---
title: "QK-Norm"
type: "concept"
category: "AI_Fundamental"
tags: ["normalization", "training", "stability"]
created: "2026-04-22"
updated: "2026-04-22"
sources: ["sources/llm_architecture_gallery.md"]
---

# QK-Norm

QK-Norm normalizes query and key projections separately before attention computation to improve training stability.

## How It Works

Before computing attention scores:
```
Q = Q / ||Q|| * scale_factor
K = K / ||K|| * scale_factor
```

This prevents attention scores from growing too large during training.

## Characteristics

- **Training stability**: Prevents gradient explosion
- **Independent normalization**: Separate normalization per head
- **Simple addition**: No extra parameters, just scaling

## Impact

- Allows higher learning rates
- Reduces training instability
- Enables larger models

## Used By

- OLMo 2 / 3
- Qwen3 series
- Gemma 3 / 4
- MiniMax M2
- GLM-4.5 / 4.7

## Related Concepts

- [MHA](./multi_head_attention.md) - Often combined with QK-Norm
- [GQA](./grouped_query_attention.md) - Alternative attention mode

---

## Source

- [LLM Architecture Gallery](../sources/llm_architecture_gallery.md)