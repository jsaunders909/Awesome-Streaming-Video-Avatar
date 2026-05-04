# Awesome Video-based Streaming Avatar Generation

A curated list of papers, resources, and systems dedicated to **Video-based Streaming and Real-time Interactive Avatar Generation**. 

This list focuses on the latest advancements (2024-2026) in making video diffusion models and autoregressive video generation architectures causal, streamable, and capable of real-time full-duplex interactions.

---

## Table of Contents
-(#surveys--benchmarks)
-(#causal-video-generation--streaming-architecture-foundations)
-(#real-time--streaming-talking-head-generation)
-(#interactive--full-duplex-conversational-avatars)

---

## Surveys & Benchmarks

* **Talking-Head Generation in Practice**
  * *ACM TheWebConf Workshop 2026*
  * A comprehensive longitudinal analysis of over 100 influential works from 2021 to 2025, revealing the community's shift toward semantic alignment, temporal coherence, and the need for rigorous benchmarks for real-time systems.[1]
* **A Survey of Interactive Generative Video**
  * *arXiv 2025.04*
  * Decomposes interactive generative video systems into modules like generation, control, and dynamics, exploring their application in areas like embodied AI and gaming.

## Causal Video Generation & Streaming Architecture (Foundations)

* **Causal Forcing: Autoregressive Diffusion Distillation Done Right for High-Quality Real-Time Interactive Video Generation**
  * *arXiv 2026.02* | [Code](https://thu-ml.github.io/CausalForcing.github.io/)
  * Identifies a mathematical fallacy in prior self-forcing methods and proposes ODE distillation initialization using an autoregressive teacher to bridge the architectural gap, enabling real-time streaming on a single RTX 4090.
* **SoulX-LiveAct: Towards Hour-Scale Real-Time Human Animation with Neighbor Forcing and ConvKV Memory**
  * *arXiv 2026.03* | [Code](https://github.com/Soul-AILab/SoulX-LiveAct)
  * Solves the long-horizon memory limit by introducing Neighbor Forcing and a structured ConvKV memory mechanism, achieving 20 FPS hour-scale real-time streaming inference with constant memory.
* **EchoTorrent: Towards Swift, Sustained, and Streaming Multi-Modal Video Generation**
  * *arXiv 2026.02* | [Code](https://github.com/antgroup/echomimic_v3)
  * Proposes a fourfold schema including Multi-Teacher Training and Hybrid Long Tail Forcing to eliminate spatiotemporal degradation and lip desynchronization during streaming inference.
* **Towards One-step Causal Video Generation via Adversarial Self-Distillation**
  * *arXiv 2025.11*
  * Uses an Adversarial Self-Distillation (ASD) strategy that aligns the outputs of the student model's n-step denoising process with its (n+1)-step version, allowing high-quality synthesis with extremely limited steps.
* **High-Fidelity Causal Video Diffusion Models for Real-Time Ultra-Low-Bitrate Semantic Communication**
  * *arXiv 2026.02*
  * Extends a modular video diffusion model using an efficient temporal distillation procedure to enable causal synthesis under ultra-low bitrate constraints.

## Real-Time & Streaming Talking Head Generation

* **StreamAvatar: Streaming Diffusion Models for Real-Time Interactive Human Avatars**
  * *CVPR 2026* | [Project](https://streamavatar.github.io)
  * Applies a two-stage autoregressive adaptation and acceleration framework (including block-wise causal attention) to convert high-fidelity non-causal diffusion models into streaming architectures.[2]
* **Live Avatar: Streaming Real-time Audio-Driven Avatar Generation with Infinite Length**
  * *arXiv 2025.12*
  * A 14B-parameter framework that leverages Timestep-forcing Pipeline Parallelism and a Rolling Sink Frame Mechanism to achieve an unprecedented 20 FPS end-to-end generation speed without identity drift.
* **REST: Diffusion-based Real-time End-to-end Streaming Talking Head Generation via ID-Context Caching...**
  * *arXiv 2025.12*
  * The first end-to-end method to achieve real-time streaming audio-driven talking head diffusion on a single GPU by introducing a novel ID-Context Cache mechanism.
* **PersonaLive!: Expressive Portrait Image Animation for Live Streaming**
  * *CVPR 2026* | [Code](https://github.com/GVCLab/PersonaLive)
  * Introduces an appearance distillation strategy and a micro-chunk streaming generation paradigm to deliver robust, streamable portrait animation up to 22× faster than previous models.
* **Knot Forcing: Taming Autoregressive Video Diffusion Models for Real-time Infinite Interactive Portrait Animation**
  * *arXiv 2025.12* | [Code](https://github.com/HumanAIGC)
  * Achieves infinite-sequence interactive portrait animation and stable real-time generation on consumer-grade GPUs by mitigating error accumulation in causal autoregressive models.
* **LLIA (Low-Latency Interactive Avatars)**
  * *arXiv 2025.06* | [Project](https://meigen-ai.github.io/llia/)
  * Utilizes INT8 model quantization and UNet/VAE pipeline parallelism to drop the initial response latency to 140ms, achieving 78 FPS at 384x384 resolution.[3]

## Interactive & Full-Duplex Conversational Avatars

* **LPM 1.0: Video-based Character Performance Model**
  * *arXiv 2026.04* | [Project](https://large-performance-model.github.io)
  * Based on a 17B-parameter Diffusion Transformer, this is the first full-duplex video generation system capable of simultaneously driving speaking, listening, and micro-expressions over long conversational horizons.
* **EmbodiedHead: Real-Time Listening and Speaking Avatar for Conversational Agents**
  * *arXiv 2026.04*
  * Replaces look-ahead audio buffers with a single-stream interface and explicit per-frame listening-speaking state modulation. Couples a Rectified-Flow DiT with a differentiable renderer for rapid generation.
* **Avatar Forcing: Real-Time Interactive Head Avatar Generation for Natural Conversation**
  * *CVPR 2026* | [Code](https://github.com/TaekyungKi/AvatarForcing)
  * Models interactions using diffusion forcing and introduces a Direct Preference Optimization (DPO) method for learning expressive and vibrant avatar reactions without additional labeled data.
* **ARIG: Autoregressive Interactive Head Generation for Real-time Conversations**
  * *ICCV 2025* | [Project](https://jinyugy21.github.io/ARIG/)
  * Formulates motion prediction as a continuous non-vector-quantized autoregressive process, employing a deep Conversational State Understanding (CSU) module to generate appropriate feedback, pauses, and interruption behaviors.[4]
