---
title: "LLM Architecture Gallery"
type: "source"
category: "AI_Fundamental"
tags: ["llm", "architecture", "models", "deepseek", "qwen", "gemma", "llama", "moe"]
created: "2026-04-22"
updated: "2026-04-22"
sources: ["raw/llm_architecture_gallery.md"]
related_topics: ["topics/ai_landscape.md", "topics/foundation_models.md"]
---

# LLM Architecture Gallery

**Author**: Sebastian Raschka, PhD
**Website**: https://sebastianraschka.com/llm-architecture-gallery/
**Last Updated**: April 10, 2026

## Overview

The LLM Architecture Gallery is a comprehensive collection of 70+ LLM architecture factsheets from Sebastian Raschka's blog. It provides architecture figures, fact sheets, comparison tools, and KV cache calculations.

## Models Covered (70+)

### Dense Models
| Model | Scale | Date |
|-------|-------|------|
| GPT-2 XL | 1.5B | 2019-11-05 |
| Llama 3 | 8B | 2024-04-18 |
| Llama 3.2 | 1B | 2024-09-25 |
| OLMo 2 | 7B | 2024-11-25 |
| Gemma 3 | 27B | 2025-03-11 |
| Mistral Small 3.1 | 24B | 2025-03-18 |
| Qwen3 | 4B-32B | 2025-04-28 |
| SmolLM3 | 3B | 2025-06-19 |
| OLMo 3 | 7B-32B | 2025-11-20 |
| Gemma 4 | 31B | 2026-03-11 |

### MoE Models
| Model | Total/Active | Date |
|------|-------------|------|
| DeepSeek V3 | 671B/37B | 2024-12-26 |
| DeepSeek R1 | 671B/37B | 2025-01-20 |
| Llama 4 Maverick | 400B/17B | 2025-04-05 |
| Qwen3 | 235B/22B | 2025-04-28 |
| Kimi K2 | 1T/32B | 2025-07-10 |
| GLM-4.5 | 355B/32B | 2025-07-28 |
| Grok 2.5 | 270B | 2025-08-22 |
| Qwen3 Next | 80B/3B | 2025-09-09 |
| MiniMax M2 | 230B/10B | 2025-10-23 |
| Kimi Linear | 48B/3B | 2025-10-30 |
| DeepSeek V3.2 | 671B/37B | 2025-12-01 |
| Mistral Large 3 | 673B/41B | 2025-12-02 |
| GLM-5 | 744B/40B | 2026-02-11 |

## Key Architecture Concepts

### Attention Mechanisms
- **MHA**: Multi-Head Attention - classic full attention
- **GQA**: Grouped-Query Attention - shares KV heads
- **MLA**: Multi-Latent Attention - DeepSeek's latent KV
- **SWA**: Sliding-Window Attention - local context
- **QK-Norm**: Query/Key normalization
- **NoPE**: No Positional Encoding

### MoE Patterns
- Sparse MoE: Routes to subset of experts
- Hybrid MoE: Transformer + state space models
- Gated Attention: Learned gating
- Latent MoE: Latent space routing

## Tools Available

- Architecture diff tool for comparing two models
- KV cache calculations
- AA Intelligence Index scores
- From-scratch implementations

## Related Topics

- [AI Landscape](../topics/ai_landscape.md)
- [Foundation Models](../topics/foundation_models.md)

---

## Source

- [Raw Source](../../raw/llm_architecture_gallery.md)
- [Website](https://sebastianraschka.com/llm-architecture-gallery/)
- [GitHub](https://github.com/rasbt/LLMs-from-scratch)