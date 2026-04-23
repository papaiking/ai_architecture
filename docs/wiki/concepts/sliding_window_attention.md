---
title: "SWA - Sliding-Window Attention"
type: "concept"
category: "AI_Fundamental"
tags: ["attention", "local", "llm"]
created: "2026-04-22"
updated: "2026-04-22"
sources: ["sources/llm_architecture_gallery.md"]
---

# SWA - Sliding-Window Attention

Sliding-Window Attention restricts each token to attend only to nearby tokens within a fixed window, trading long-range context for efficiency.

## How It Works

Each token can only attend to tokens within a fixed window size (e.g., 128 tokens). Local attention captures short-range dependencies while global attention layers handle longer context.

## Characteristics

- **Local focus**: Tokens only see nearby context
- **Lower complexity**: O(w*n) instead of O(n²)
- **Mixed approach**: Often interleaved with global layers

## Window Size

Common window sizes:
- **128 tokens**: Gemma 3 uses 5:1 ratio (128 local + global)
- **2048 tokens**: Some larger models

## Mixed Layer Configuration

Many models use hybrid approach:
- Gemma 3 (27B): 52 sliding-window + 10 global layers
- OLMo 3 (7B): 24 sliding-window + 8 global layers
- Xiaomi MiMo-V2-Flash: 40 sliding-window + 8 global

## Used By

- Gemma 3
- Mistral Small 3.1
- GPT-OSS
- OLMo 3
- Xiaomi MiMo-V2-Flash

## Related Concepts

- [GQA](./grouped_query_attention.md) - Often combined with SWA
- [QK-Norm](./qk_norm.md) - Stabilization technique

---

## Source

- [LLM Architecture Gallery](../sources/llm_architecture_gallery.md)