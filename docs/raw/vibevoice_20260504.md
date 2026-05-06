# VibeVoice: Open-Source Frontier Voice AI

**Project Page**: https://microsoft.github.io/VibeVoice  
**GitHub**: https://github.com/microsoft/VibeVoice  
**Hugging Face**: https://huggingface.co/collections/microsoft/vibevoice-68a2ef24a875c44be47b034f  
**License**: Research use only (removed TTS code due to misuse)

## News

- 2026-03-06: VibeVoice ASR now part of Hugging Face Transformers release
- 2026-01-21: Open-sourced VibeVoice-ASR (60-minute long-form ASR, 50+ languages, finetuning code, vLLM inference)
- 2025-12-16: Added experimental speakers to VibeVoice-Realtime-0.5B (9 languages, 11 English style voices)
- 2025-12-03: Open-sourced VibeVoice-Realtime-0.5B (real-time streaming TTS)
- 2025-09-05: VibeVoice-TTS code removed from repo due to misuse
- 2025-08-25: Open-sourced VibeVoice-TTS (90-minute long-form multi-speaker TTS, ICLR 2026 Oral)

## Overview

VibeVoice is a **family of open-source frontier voice AI models** from Microsoft that includes both TTS and ASR models.

Core innovation: continuous speech tokenizers (Acoustic and Semantic) at **7.5 Hz** ultra-low frame rate, preserving audio fidelity while boosting computational efficiency. Uses [next-token diffusion](https://arxiv.org/abs/2412.08635) framework with LLM for text context and diffusion head for acoustic details.

## Models

### VibeVoice-ASR-7B - Long-form Speech Recognition

- **60-minute Single-Pass Processing**: Handles up to 60 minutes continuous audio in 64K token length
- **Customized Hotwords**: Domain-specific names, terms, background info
- **Rich Transcription (Who, When, What)**: Joint ASR, diarization, and timestamping
- **50+ languages** supported
- Finetuning code and vLLM inference available

[Playground](https://aka.ms/vibevoice-asr) | [Hugging Face](https://huggingface.co/microsoft/VibeVoice-ASR)

### VibeVoice-TTS-1.5B - Long-form Multi-speaker TTS (ICLR 2026 Oral)

- **90-minute Long-form Generation**: Single pass, consistent speaker and semantic coherence
- **Multi-speaker Support**: Up to 4 distinct speakers, natural turn-taking
- **Expressive Speech**: Conversational dynamics and emotional nuances
- **Multi-lingual**: English, Chinese, and other languages

⚠️ Code removed from repo due to misuse. Model weights still available.

[Hugging Face](https://huggingface.co/microsoft/VibeVoice-1.5B) | [Paper](https://arxiv.org/pdf/2508.19205)

### VibeVoice-Realtime-0.5B - Real-time Streaming TTS

- 0.5B parameters (deployment-friendly)
- Real-time TTS (~300ms first audible latency)
- Streaming text input
- Robust long-form speech generation (~10 minutes)
- Experimental speakers: 9 languages (DE, FR, IT, JP, KR, NL, PL, PT, ES), 11 English style voices

[Colab](https://colab.research.google.com/github/microsoft/VibeVoice/blob/main/demo/vibevoice_realtime_colab.ipynb) | [Hugging Face](https://huggingface.co/microsoft/VibeVoice-Realtime-0.5B)

## Tech Stack

- Base model: Qwen2.5 1.5B
- Continuous speech tokenizers at 7.5 Hz
- Next-token diffusion framework
- LLM for text context understanding
- Diffusion head for acoustic detail generation

## Risks and Limitations

- Inherits biases from Qwen2.5 1.5B base model
- Potential for deepfakes and disinformation
- Research and development purposes only
- Not recommended for commercial use without further testing
