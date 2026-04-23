---
title: "MLA - Multi-Latent Attention"
type: "concept"
category: "AI_Fundamental"
tags: ["attention", "deepseek", "llm"]
created: "2026-04-22"
updated: "2026-04-22"
sources: ["sources/llm_architecture_gallery.md"]
---

# MLA - Multi-Latent Attention

Multi-Latent Attention is DeepSeek's innovation that uses low-rank compressed latent vectors instead of full KV for significantly reduced KV cache.

## How It Works

1. **Compress**: Project Q, K, V into lower-dimensional latent space
2. **Decompress**: Expand latent back to attention dimensions during computation
3. **Store only latent**: Save compressed representation

## Characteristics

- **Lowest KV cache**: Uses ~5x less cache than standard attention
- **High efficiency**: Enables very large models at reasonable inference cost
- **DeepSeek innovation**: First introduced in DeepSeek V2

## KV Cache Size

Very low - approximately 68.6 KiB per token at 671B scale.

Used by DeepSeek V3, DeepSeek R1, Mistral Large 3.

## Used By

- DeepSeek V3 / V3.2
- DeepSeek R1
- Mistral Large 3
- Kimi K2
- Kimi Linear

## Related Concepts

- [GQA](./grouped_query_attention.md) - Alternative efficient approach
- [DeepSeek Sparse Attention](./deepseek_sparse_attention.md) - Evolutionary update

---

## Source

- [LLM Architecture Gallery](../sources/llm_architecture_gallery.md)