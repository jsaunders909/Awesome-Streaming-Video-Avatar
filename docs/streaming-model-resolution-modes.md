# Streaming Avatar Models: Resolution & Streaming Modes

This note summarizes the current streaming and real-time avatar models in the list, with a focus on:

- reported or inferable output / training resolution
- streaming granularity and causality
- reported latency or throughput
- practical deployment implications

> Note: many papers report training crop resolution, VAE compression ratio, or benchmark settings rather than a guaranteed production output resolution. In those cases, the resolution is marked as not explicitly stated.

## High-Level Takeaways

- **512x512 is the clearest practical target** among current pixel-level diffusion-style streaming avatar systems.
- **720p+ low-latency streaming is not yet consistently demonstrated** for these avatar diffusion systems; several works explicitly reduce resolution to satisfy real-time constraints.
- **Frame-level or very short chunk autoregressive systems** are best suited for live interaction latency.
- **Pixel-level diffusion systems** generally provide stronger visual fidelity but require heavier serving infrastructure.
- **Motion / renderer based systems** can reach much lower latency, but may trade off full pixel-level generative flexibility.

## Model Comparison

| Model | Reported Resolution | Use Case | Streaming Mode | Reported Speed | Practical Read |
| --- | --- | --- | --- | --- | --- |
| [Hallo-Live](https://arxiv.org/abs/2604.23632) | Not explicitly stated in inspected text | Text-to-audio-video joint generation | Asynchronous dual-stream diffusion. The video stream commits the current block, while the audio stream carries current plus temporary future audio. Uses Future-Expanding Attention. | 20.38 FPS, 0.94s latency on 2xH200 | True streaming with one-block / one-frame audio look-ahead. |
| [SoulX-FlashHead](https://arxiv.org/abs/2602.07449) | 512x512 reported training / data crop | Audio-driven portrait | Autoregressive streaming DiT with Temporal Audio Context Cache. Lite uses LTX-style 32x32x8 compression. Uses Oracle-Guided Bidirectional Distillation. | Lite: 96 FPS on RTX 4090 | Strong consumer-GPU candidate among diffusion-style portrait models. |
| [SoulX-FlashTalk](https://arxiv.org/abs/2512.23379) | Reduced spatial resolution; exact output size not stated | Audio-driven full-body / avatar | Chunk-based streaming. Retains bidirectional attention inside the current chunk, with self-correcting bidirectional distillation and multi-step retrospective correction. | 32 FPS, 0.87s startup on 8xH800 | High-quality 14B route; heavy multi-GPU serving. |
| [REST](https://arxiv.org/abs/2512.11229) | 512x512, 97-frame training chunks | Audio-driven talking head | Semi-autoregressive diffusion. Uses temporal VAE 32x32x8, ID-Sink plus previous-chunk Context Cache, and ASD from a non-streaming teacher to a streaming student. | 4.416s runtime for 121 frames on A100 setup | Strong explicit 512x512 streaming diffusion setup with single-GPU real-time claim. |
| [TalkingMachines](https://arxiv.org/abs/2506.03099) | 512x512 target; supports aspect ratios within the same pixel area | FaceTime-style audio-driven character video | Sparse causal AR diffusion student. An 81-frame clip is split into 7 chunks of 3 latent frames; each chunk attends to the current chunk, previous chunk, and first-image anchor. | Real-time via 2-step distillation plus DiT/VAE disaggregation; exact FPS not stated in inspected text | Practical serving-oriented design; explicitly notes 720x720 is much more expensive. |
| [DyStream](https://arxiv.org/abs/2512.24408) | Not explicitly stated | Dyadic talking head | Frame-by-frame autoregressive audio-to-motion generation with LivePortrait/LIA-style warp decoder. Uses causal Wav2Vec2 with about 60ms look-ahead. | Less than 34ms per frame; less than 40ms per incoming audio packet | Lowest-latency interaction shape; more motion / renderer based than full pixel diffusion. |
| [EmbodiedHead](https://arxiv.org/abs/2604.17211) | Rendered avatar resolution not stated | 3D head avatar for LLM conversation | Single audio stream with per-frame listening/speaking state. Uses Streaming Audio Scheduler, Rectified-Flow DiT over FLAME motion, and differentiable renderer. | Few-step generation with 4 sampling steps; paper claims real-time | Good architecture for LLM turn-taking because it avoids dual-audio look-ahead dependency. |
| [Beyond Monologue](https://arxiv.org/abs/2604.10367) | Not explicitly stated | Full-duplex talking/listening human video | Wan2.2 5B backbone with dual talking/listening audio streams, 4x16x16 VAE compression, Gaussian temporal kernels, and diffusion forcing. | No explicit FPS/latency found in inspected text | More focused on full-duplex behavior modeling than low-latency systems serving. |
| [StableAvatar](https://arxiv.org/abs/2508.08248) | Not explicitly stated in inspected text | Long-form audio-driven avatar | Weighted sliding-window denoising with audio-native guidance, designed for infinite-length consistency. | 30 FPS examples; 3500+ frames / 3+ minutes reported | Long-video stability oriented, not necessarily interactive streaming. |
| [TurboTalk](https://arxiv.org/abs/2604.14580) | Not explicitly stated | Audio-driven talking avatar | Progressive distillation from a multi-step teacher to a 4-step student and then a 1-step generator. | 120x inference speedup; exact FPS/latency not stated | Acceleration method; not a complete streaming-mode system by itself. |

## Practical Buckets

### Lowest Latency

- **DyStream**: frame-by-frame AR generation with minimal audio look-ahead.
- **EmbodiedHead**: 3D/motion-first pipeline for real-time LLM turn-taking.

These are better references for conversational responsiveness than for full pixel-level video generation.

### Strong 512x512 Pixel-Level References

- **REST**: explicit 512x512 streaming diffusion training setup.
- **SoulX-FlashHead**: 512x512 portrait data/crop and very high reported FPS for the Lite version.
- **TalkingMachines**: explicitly targets 512x512 and discusses why higher resolution is harder for streaming.

These are the clearest references for practical high-fidelity streaming avatar video at current compute levels.

### Heavy High-Fidelity Serving

- **SoulX-FlashTalk**: 14B model, 8xH800 reported setup.
- **Hallo-Live**: joint audio-video generation on 2xH200 with sub-second latency.

These are more suitable as high-quality service architectures than consumer deployment baselines.

## Resolution Trend

Current streaming avatar systems mostly converge around **512x512** for real-time or near-real-time pixel-level generation. Higher resolutions such as 720p or 1080p remain costly because the video token count grows quickly, increasing transformer attention cost, VAE decoding cost, and activation memory.

For practical product design today:

- use **512x512** as the default target for pixel-level diffusion avatar streaming
- use **motion/renderer-based systems** when sub-100ms response is more important than generative flexibility
- treat **720p+** as an upscaling or post-processing target unless the serving stack has substantial multi-GPU capacity
