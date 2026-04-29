---
title: "Poolside Laguna"
type: "source"
category: "AI_Fundamental"
tags: ["llm", "open-source", "coding", "agentic", "moe", "poolside"]
created: "2026-04-28"
updated: "2026-04-28"
sources: ["raw/poolside_laguna.md"]
related_topics: ["topics/llm.md", "topics/llm_inference.md"]
---

# Poolside Laguna

**Organization**: Poolside
**Website**: https://poolside.ai/
**GitHub**: https://github.com/poolsideAI

## Overview

American AI startup Poolside launched free, high-performing open model Laguna XS.2 for local agentic coding.

## Models

### Laguna M.1
- **Parameters**: 225B total, 23B active (MoE)
- **Target**: Enterprise & government (complex software engineering)
- **Access**: Free via API, OpenRouter, Ollama

### Laguna XS.2 ⭐
- **Parameters**: 33B total, 3B active (MoE)
- **License**: Apache 2.0 (open source)
- **Target**: Local agentic coding on consumer hardware
- **Download**: Hugging Face, Ollama

## Benchmark Results

| Model | SWE-bench Pro | vs |
|-------|--------------|-----|
| Laguna M.1 | 46.9% | Near Qwen3.5, DeepSeek V4 |
| Laguna XS.2 | 44.5% | Beats Claude Haiku 4.5 (39.5%) |

## Technical Requirements

| Platform | Requirement |
|----------|-----------|
| Mac | 36 GB RAM (M5 Max) |
| PC GPU | 24 GB VRAM (RTX 4090+) |
| Storage | 20-70 GB |

## Products

- **pool**: Terminal-based coding agent
- **shimmer**: Mobile-optimized cloud IDE

## Related Topics

- [Generative AI and LLM](../topics/llm.md)

---

## Source

- [Raw Source](../../raw/poolside_laguna.md)
- [Website](https://poolside.ai/)
- [Hugging Face](https://huggingface.co/collections/poolside/laguna-xs2)