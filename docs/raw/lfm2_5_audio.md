---
title: "LFM2.5-Audio-1.5B"
type: "source"
category: "AI_Fundamental"
tags: ["audio", "foundation model", "speech", "ASR", "TTS", "multimodal"]
created: "2026-04-21"
updated: "2026-04-21"
sources: ["https://huggingface.co/LiquidAI/LFM2.5-Audio-1.5B"]
---

# LFM2.5-Audio-1.5B

**Organization**: Liquid AI
**Model**: 1.5B parameters

## Overview

Liquid AI's updated end-to-end audio foundation model. End-to-end multimodal speech and text language model - does not require separate ASR and TTS components.

## Key Improvements

- Custom, LFM based audio detokenizer
- llama.cpp compatible GGUFs for CPU inference
- Better ASR and TTS performance
- Low latency for real-time conversation

## Architecture

The model consists of:

- **Pretrained LFM2.5** as multimodal backbone
- **FastConformer** based audio encoder for continuous audio inputs
- **RQ-transformer** generating discrete tokens
- **Lightweight audio detokenizer** for audio output

## Generation Modes

### Interleaved Generation
- Real-time speech-to-speech conversational chatbot
- Audio generation latency is key

### Sequential Generation
- Non-conversational tasks (ASR, TTS)
- Allows model to switch generated modality on the fly

## Capabilities

- **1.5B parameters** achieves capabilities on par with much larger models
- Seamless conversational interaction
- Low latency design
- Multimodal speech + text

---

## Source

- [Wiki Source](../wiki/sources/lfm2_5_audio.md)
- [HuggingFace](https://huggingface.co/LiquidAI/LFM2.5-Audio-1.5B)
- [GitHub Cookbook](https://github.com/Liquid4All/cookbook)