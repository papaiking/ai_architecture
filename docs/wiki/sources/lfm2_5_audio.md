---
title: "LFM2.5-Audio-1.5B"
type: "source"
category: "AI_Fundamental"
tags: ["audio", "foundation model", "speech", "ASR", "TTS", "multimodal"]
created: "2026-04-21"
updated: "2026-04-21"
sources: ["raw/lfm2_5_audio.md"]
related_topics: ["topics/ai_landscape.md", "topics/foundation_models.md"]
---

# LFM2.5-Audio-1.5B

- **Organization**: Liquid AI
- **Model**: 1.5B parameters

## Overview

Liquid AI's updated end-to-end audio foundation model. Does not require separate ASR and TTS components.

## Key Features

- **End-to-end**: Multimodal speech and text language model
- **Low latency**: Designed for real-time conversation
- **1.5B parameters**: Achieves capabilities on par with much larger models
- **GGUF support**: llama.cpp compatible for CPU inference

## Architecture

- **Backbone**: Pretrained LFM2.5 multimodal
- **Audio Encoder**: FastConformer
- **Token Generation**: RQ-transformer
- **Audio Output**: Lightweight audio detokenizer

## Generation Modes

| Mode | Use Case |
|------|----------|
| Interleaved | Real-time speech-to-speech conversation |
| Sequential | ASR, TTS, switch modality on the fly |

---

## Related Topics

- [AI Landscape](../topics/ai_landscape.md)
- [Foundation Models](../topics/foundation_models.md)

---

## Source

- [Raw Source](../../raw/lfm2_5_audio.md)
- [HuggingFace](https://huggingface.co/LiquidAI/LFM2.5-Audio-1.5B)