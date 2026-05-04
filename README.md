# Awesome Video-Based Streaming Avatar Generation [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

A curated list of papers, projects, and resources for **video-based streaming** and **real-time interactive avatar generation**.

This repository focuses on recent advances in making **video diffusion models** and **autoregressive video generation architectures** more **causal**, **streamable**, and suitable for **real-time full-duplex interaction**, with an emphasis on the 2024–2026 wave of progress.

> Contributions are welcome. Please read the [Contributing](#contributing) section before submitting a pull request.

---

## Badges

![Coverage](https://img.shields.io/badge/coverage-2024--2026-blue?style=flat-square)
![Topic](https://img.shields.io/badge/topic-streaming%20avatars-0A66C2?style=flat-square)
![Focus](https://img.shields.io/badge/focus-real--time%20interactive-success?style=flat-square)
![Maintenance](https://img.shields.io/badge/status-actively%20curated-brightgreen?style=flat-square)

### Tag Legend

- ![Survey](https://img.shields.io/badge/-Survey-purple?style=flat-square)
- ![Benchmark](https://img.shields.io/badge/-Benchmark-6f42c1?style=flat-square)
- ![Causal](https://img.shields.io/badge/-Causal-1f6feb?style=flat-square)
- ![Streaming](https://img.shields.io/badge/-Streaming-0ea5e9?style=flat-square)
- ![Real-time](https://img.shields.io/badge/-Real--time-16a34a?style=flat-square)
- ![Interactive](https://img.shields.io/badge/-Interactive-f59e0b?style=flat-square)
- ![Full-duplex](https://img.shields.io/badge/-Full--duplex-dc2626?style=flat-square)
- ![Talking Head](https://img.shields.io/badge/-Talking%20Head-64748b?style=flat-square)

---

## Table of Contents

- [Surveys \& Benchmarks](#surveys--benchmarks)
- [Causal Video Generation \& Streaming Architecture](#causal-video-generation--streaming-architecture)
- [Real-Time \& Streaming Talking Head Generation](#real-time--streaming-talking-head-generation)
- [Interactive \& Full-Duplex Conversational Avatars](#interactive--full-duplex-conversational-avatars)
- [Contributing](#contributing)
- [License](#license)

---

## Surveys & Benchmarks

- **Talking-Head Generation in Practice**  
  ![Survey](https://img.shields.io/badge/-Survey-purple?style=flat-square)
  ![Talking Head](https://img.shields.io/badge/-Talking%20Head-64748b?style=flat-square)
  ![Benchmark](https://img.shields.io/badge/-Benchmark-6f42c1?style=flat-square)  
  *ACM TheWebConf Workshop 2026*  
  A comprehensive longitudinal analysis of over 100 influential works from 2021 to 2025, highlighting the field’s shift toward semantic alignment, temporal coherence, and the need for rigorous benchmarks for real-time systems.

- **A Survey of Interactive Generative Video**  
  ![Survey](https://img.shields.io/badge/-Survey-purple?style=flat-square)
  ![Interactive](https://img.shields.io/badge/-Interactive-f59e0b?style=flat-square)  
  *arXiv 2025.04*  
  A modular survey of interactive generative video systems, covering generation, control, and dynamics, with applications to embodied AI, gaming, and beyond.

---

## Causal Video Generation & Streaming Architecture

- **Causal Forcing: Autoregressive Diffusion Distillation Done Right for High-Quality Real-Time Interactive Video Generation**  
  ![Causal](https://img.shields.io/badge/-Causal-1f6feb?style=flat-square)
  ![Streaming](https://img.shields.io/badge/-Streaming-0ea5e9?style=flat-square)
  ![Real-time](https://img.shields.io/badge/-Real--time-16a34a?style=flat-square)
  ![Interactive](https://img.shields.io/badge/-Interactive-f59e0b?style=flat-square)  
  *arXiv 2026.02* · [Project / Code](https://thu-ml.github.io/CausalForcing.github.io/)  
  Identifies a mathematical issue in prior self-forcing methods and proposes ODE distillation initialization with an autoregressive teacher, enabling high-quality real-time streaming on a single RTX 4090.

- **SoulX-LiveAct: Towards Hour-Scale Real-Time Human Animation with Neighbor Forcing and ConvKV Memory**  
  ![Causal](https://img.shields.io/badge/-Causal-1f6feb?style=flat-square)
  ![Streaming](https://img.shields.io/badge/-Streaming-0ea5e9?style=flat-square)
  ![Real-time](https://img.shields.io/badge/-Real--time-16a34a?style=flat-square)  
  *arXiv 2026.03* · [Code](https://github.com/Soul-AILab/SoulX-LiveAct)  
  ![GitHub Repo stars](https://img.shields.io/github/stars/Soul-AILab/SoulX-LiveAct?style=flat-square)
  ![GitHub top language](https://img.shields.io/github/languages/top/Soul-AILab/SoulX-LiveAct?style=flat-square)  
  Solves long-horizon memory bottlenecks with Neighbor Forcing and structured ConvKV memory, achieving hour-scale real-time streaming inference at 20 FPS with constant memory usage.

- **EchoTorrent: Towards Swift, Sustained, and Streaming Multi-Modal Video Generation**  
  ![Causal](https://img.shields.io/badge/-Causal-1f6feb?style=flat-square)
  ![Streaming](https://img.shields.io/badge/-Streaming-0ea5e9?style=flat-square)  
  *arXiv 2026.02* · [Code](https://github.com/antgroup/echomimic_v3)  
  ![GitHub Repo stars](https://img.shields.io/github/stars/antgroup/echomimic_v3?style=flat-square)
  ![GitHub top language](https://img.shields.io/github/languages/top/antgroup/echomimic_v3?style=flat-square)  
  Proposes a four-part training and inference scheme, including Multi-Teacher Training and Hybrid Long Tail Forcing, to reduce streaming artifacts such as spatiotemporal degradation and lip desynchronization.

- **Towards One-step Causal Video Generation via Adversarial Self-Distillation**  
  ![Causal](https://img.shields.io/badge/-Causal-1f6feb?style=flat-square)
  ![Real-time](https://img.shields.io/badge/-Real--time-16a34a?style=flat-square)  
  *arXiv 2025.11*  
  Uses Adversarial Self-Distillation (ASD) to align the student model’s n-step denoising output with its (n+1)-step version, enabling high-quality synthesis with extremely limited denoising steps.

- **High-Fidelity Causal Video Diffusion Models for Real-Time Ultra-Low-Bitrate Semantic Communication**  
  ![Causal](https://img.shields.io/badge/-Causal-1f6feb?style=flat-square)
  ![Real-time](https://img.shields.io/badge/-Real--time-16a34a?style=flat-square)  
  *arXiv 2026.02*  
  Extends a modular video diffusion framework with efficient temporal distillation to support causal synthesis under ultra-low bitrate constraints.

---

## Real-Time & Streaming Talking Head Generation

- **StreamAvatar: Streaming Diffusion Models for Real-Time Interactive Human Avatars**  
  ![Streaming](https://img.shields.io/badge/-Streaming-0ea5e9?style=flat-square)
  ![Real-time](https://img.shields.io/badge/-Real--time-16a34a?style=flat-square)
  ![Interactive](https://img.shields.io/badge/-Interactive-f59e0b?style=flat-square)
  ![Talking Head](https://img.shields.io/badge/-Talking%20Head-64748b?style=flat-square)  
  *CVPR 2026* · [Project](https://streamavatar.github.io)  
  Converts high-fidelity non-causal diffusion models into streaming architectures with a two-stage autoregressive adaptation and acceleration framework, including block-wise causal attention.

- **Live Avatar: Streaming Real-time Audio-Driven Avatar Generation with Infinite Length**  
  ![Streaming](https://img.shields.io/badge/-Streaming-0ea5e9?style=flat-square)
  ![Real-time](https://img.shields.io/badge/-Real--time-16a34a?style=flat-square)
  ![Talking Head](https://img.shields.io/badge/-Talking%20Head-64748b?style=flat-square)  
  *arXiv 2025.12*  
  A 14B-parameter framework that leverages Timestep-forcing Pipeline Parallelism and a Rolling Sink Frame Mechanism to achieve 20 FPS end-to-end generation without identity drift.

- **REST: Diffusion-based Real-time End-to-end Streaming Talking Head Generation via ID-Context Caching...**  
  ![Streaming](https://img.shields.io/badge/-Streaming-0ea5e9?style=flat-square)
  ![Real-time](https://img.shields.io/badge/-Real--time-16a34a?style=flat-square)
  ![Talking Head](https://img.shields.io/badge/-Talking%20Head-64748b?style=flat-square)  
  *arXiv 2025.12*  
  The first end-to-end method to achieve real-time streaming audio-driven talking head diffusion on a single GPU, enabled by a novel ID-Context Cache mechanism.

- **PersonaLive!: Expressive Portrait Image Animation for Live Streaming**  
  ![Streaming](https://img.shields.io/badge/-Streaming-0ea5e9?style=flat-square)
  ![Real-time](https://img.shields.io/badge/-Real--time-16a34a?style=flat-square)
  ![Talking Head](https://img.shields.io/badge/-Talking%20Head-64748b?style=flat-square)  
  *CVPR 2026* · [Code](https://github.com/GVCLab/PersonaLive)  
  ![GitHub Repo stars](https://img.shields.io/github/stars/GVCLab/PersonaLive?style=flat-square)
  ![GitHub top language](https://img.shields.io/github/languages/top/GVCLab/PersonaLive?style=flat-square)  
  Introduces appearance distillation and a micro-chunk streaming generation paradigm, delivering robust streamable portrait animation up to 22× faster than prior methods.

- **Knot Forcing: Taming Autoregressive Video Diffusion Models for Real-time Infinite Interactive Portrait Animation**  
  ![Streaming](https://img.shields.io/badge/-Streaming-0ea5e9?style=flat-square)
  ![Real-time](https://img.shields.io/badge/-Real--time-16a34a?style=flat-square)
  ![Interactive](https://img.shields.io/badge/-Interactive-f59e0b?style=flat-square)
  ![Talking Head](https://img.shields.io/badge/-Talking%20Head-64748b?style=flat-square)  
  *arXiv 2025.12* · [Code](https://github.com/HumanAIGC)  
  Achieves infinite-sequence interactive portrait animation and stable real-time generation on consumer-grade GPUs by reducing error accumulation in causal autoregressive models.

- **LLIA (Low-Latency Interactive Avatars)**  
  ![Real-time](https://img.shields.io/badge/-Real--time-16a34a?style=flat-square)
  ![Interactive](https://img.shields.io/badge/-Interactive-f59e0b?style=flat-square)
  ![Talking Head](https://img.shields.io/badge/-Talking%20Head-64748b?style=flat-square)  
  *arXiv 2025.06* · [Project](https://meigen-ai.github.io/llia/)  
  Uses INT8 quantization and UNet/VAE pipeline parallelism to reduce initial response latency to 140 ms, achieving 78 FPS at 384×384 resolution.

---

## Interactive & Full-Duplex Conversational Avatars

- **LPM 1.0: Video-based Character Performance Model**  
  ![Interactive](https://img.shields.io/badge/-Interactive-f59e0b?style=flat-square)
  ![Full-duplex](https://img.shields.io/badge/-Full--duplex-dc2626?style=flat-square)  
  *arXiv 2026.04* · [Project](https://large-performance-model.github.io)  
  Built on a 17B-parameter Diffusion Transformer, this is the first full-duplex video generation system capable of simultaneously driving speaking, listening, and micro-expressions over long conversational horizons.

- **EmbodiedHead: Real-Time Listening and Speaking Avatar for Conversational Agents**  
  ![Interactive](https://img.shields.io/badge/-Interactive-f59e0b?style=flat-square)
  ![Full-duplex](https://img.shields.io/badge/-Full--duplex-dc2626?style=flat-square)
  ![Real-time](https://img.shields.io/badge/-Real--time-16a34a?style=flat-square)  
  *arXiv 2026.04*  
  Replaces look-ahead audio buffers with a single-stream interface and explicit per-frame listening-speaking state modulation, coupling a Rectified-Flow DiT with a differentiable renderer for rapid generation.

- **Avatar Forcing: Real-Time Interactive Head Avatar Generation for Natural Conversation**  
  ![Interactive](https://img.shields.io/badge/-Interactive-f59e0b?style=flat-square)
  ![Full-duplex](https://img.shields.io/badge/-Full--duplex-dc2626?style=flat-square)
  ![Real-time](https://img.shields.io/badge/-Real--time-16a34a?style=flat-square)
  ![Talking Head](https://img.shields.io/badge/-Talking%20Head-64748b?style=flat-square)  
  *CVPR 2026* · [Code](https://github.com/TaekyungKi/AvatarForcing)  
  ![GitHub Repo stars](https://img.shields.io/github/stars/TaekyungKi/AvatarForcing?style=flat-square)
  ![GitHub top language](https://img.shields.io/github/languages/top/TaekyungKi/AvatarForcing?style=flat-square)  
  Models interactions via diffusion forcing and introduces Direct Preference Optimization (DPO) to learn expressive and vivid avatar reactions without additional labeled data.

- **ARIG: Autoregressive Interactive Head Generation for Real-time Conversations**  
  ![Interactive](https://img.shields.io/badge/-Interactive-f59e0b?style=flat-square)
  ![Real-time](https://img.shields.io/badge/-Real--time-16a34a?style=flat-square)
  ![Talking Head](https://img.shields.io/badge/-Talking%20Head-64748b?style=flat-square)  
  *ICCV 2025* · [Project](https://jinyugy21.github.io/ARIG/)  
  Formulates motion prediction as a continuous non-vector-quantized autoregressive process and uses a deep Conversational State Understanding (CSU) module to generate appropriate feedback, pauses, and interruption behaviors.

---

## Contributing

Please make sure your pull request follows these principles:

- Add resources that are relevant to **video-based streaming avatars** or closely related interactive avatar generation.
- Prefer **official project pages**, **paper links**, and **code repositories** whenever available.
- Keep entries concise and informative.
- Use the existing format and place each entry in the most appropriate section.
- Avoid duplicate entries.
- For major additions, consider including:
  - title
  - venue / year
  - official link(s)
  - one-sentence summary
  - optional GitHub badge(s), if the repository path is known

You may also find the general [Awesome list guidelines](https://github.com/sindresorhus/awesome/blob/main/awesome.md) helpful.

---

## License

This list is intended for research and educational use.

If you want to open-source this repository, a common choice is the [MIT License](https://opensource.org/licenses/MIT).  
You can add a `LICENSE` file and update this section accordingly.

---

## Acknowledgement

This repository is curated for researchers and practitioners working on:

- streaming video generation
- real-time talking head synthesis
- interactive avatar systems
- full-duplex conversational agents
- causal video modeling

If you find this repository useful, consider giving it a star.
