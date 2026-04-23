---
title: "MHA - Multi-Head Attention"
type: "concept"
category: "AI_Fundamental"
tags: ["attention", "transformer", "deep-learning"]
created: "2026-04-22"
updated: "2026-04-22"
sources: ["sources/llm_architecture_gallery.md"]
---

# MHA - Multi-Head Attention

Multi-Head Attention is the classic attention mechanism introduced in the original Transformer paper "Attention Is All You Need" (2017).

## How It Works

Each head computes its own Q (query), K (key), and V (value) projections from the input. Attention scores are computed independently per head:

```
Attention(Q, K, V) = softmax(QK^T / sqrt(d_k))V
```

Multiple heads run in parallel, allowing the model to attend to different representation subspaces simultaneously.

## Characteristics

- **Full attention**: Every token attends to every other token
- **Separate KV heads**: Each head has its own key and value projections
- **Most expressive**: Highest KV cache cost but most flexible

## KV Cache Size

Very high - each layer stores full Q, K, V matrices.

Example: OLMo 2 7B uses 512 KiB per token.

## Used By

- GPT-2 XL
- OLMo 2
- OLMo 3 (7B)

## Related Concepts

- [GQA](./grouped_query_attention.md) - More efficient alternative
- [MLA](./multi_latent_attention.md) - DeepSeek's latent KV approach
- [QK-Norm](./qk_norm.md) - Stabilized attention

---

## Source

- [LLM Architecture Gallery](../sources/llm_architecture_gallery.md)