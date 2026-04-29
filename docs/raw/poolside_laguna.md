# Poolside Laguna - Open Source AI Coding Models

**Organization**: Poolside
**Website**: https://poolside.ai/

## Overview

American AI startup Poolside launched free, high-performing open model Laguna XS.2 for local agentic coding. The company focuses on serving government and public sector clients.

## New Models

### Laguna M.1
- **Parameters**: 225B total, 23B active (MoE)
- **Target**: High-consequence enterprise and government environments
- **Use case**: Complex, long-horizon software engineering problems
- **Access**: Free via API temporarily, OpenRouter, Ollama

### Laguna XS.2
- **Parameters**: 33B total, 3B active (MoE)
- **License**: Apache 2.0 (open source)
- **Target**: Local agentic coding on consumer hardware
- **Access**: Hugging Face, Ollama (downloadable, runs offline)

## Key Features

- **Trained from scratch**: Not fine-tuned from Qwen like other U.S. labs
- **Trained on**: 30 trillion tokens using Muon optimizer
- **Synthetic data**: ~13% synthetic training data
- **Reinforcement Learning**: Uses "real-world gym" for RL training

## Benchmark Results

| Model | SWE-bench Pro | SWE-bench Verified |
|-------|--------------|-------------------|
| Laguna M.1 | 46.9% | 72.5% |
| Laguna XS.2 | 44.5% | - |

- XS.2 outperforms Claude Haiku 4.5 (39.5%) and Gemma 4 31B (35.7%)
- Near-matches M.1 despite being much smaller

## Technical Requirements (Laguna XS.2)

| Platform | Requirements |
|----------|-------------|
| Mac (Apple Silicon) | 36 GB unified memory (M5 Max) |
| PC (NVIDIA) | 24-32 GB VRAM (RTX 4090+) |
| Quantized (Q4) | 24 GB VRAM |
| Storage | 70 GB (full) / 20-35 GB (compressed) |

## Products

- **pool**: Terminal-based coding agent
- **shimmer**: Cloud-native VM sandbox, mobile-optimized IDE

## Related Links

- Website: https://poolside.ai/
- Hugging Face: https://huggingface.co/collections/poolside/laguna-xs2
- shIMMER: https://shimmer.poolside.ai/

---

**Source**: [VentureBeat](https://venturebeat.com/technology/american-ai-startup-poolside-launches-free-high-performing-open-model-laguna-xs-2-for-local-agentic-coding)
**Date**: 2026-04-28