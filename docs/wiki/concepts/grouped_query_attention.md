---
title: "GQA - Grouped-Query Attention"
type: "concept"
category: "AI_Fundamental"
tags: ["attention", "llm", "efficiency"]
created: "2026-04-22"
updated: "2026-04-22"
sources: ["sources/llm_architecture_gallery.md"]
---

# GQA - Grouped-Query Attention

Grouped-Query Attention (GQA) shares key and value heads across multiple query heads, reducing KV cache size while maintaining quality.

## How It Works

Instead of separate KV per query head, GQA groups multiple query heads that share the same KV projection:

- More query heads than KV heads
- Each group of Q heads shares one KV head

## Characteristics

- **Intermediate efficiency**: Between MHA and MQA
- **Maintains diversity**: Different query groups can attend to different aspects
- **Balanced**: Good trade-off between expressiveness and efficiency

## KV Cache Size

Moderate - reduces proportionally to the number of KV heads.

Example: Llama 3 8B uses 128 KiB per token with 8 KV heads.

## Used By

- Llama 3 / 3.2
- Llama 4 Maverick
- Qwen3 series
- Gemma 3 / 4
- Mistral Small 3.1

## Related Concepts

- [MHA](./multi_head_attention.md) - Full attention (more expensive)
- [MLA](./multi_latent_attention.md) - DeepSeek's latent approach

---

## Source

- [LLM Architecture Gallery](../sources/llm_architecture_gallery.md)