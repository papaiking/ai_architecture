---
title: "Gated Attention"
type: "concept"
category: "AI_Fundamental"
tags: ["attention", "gating", "moe"]
created: "2026-04-22"
updated: "2026-04-22"
sources: ["sources/llm_architecture_gallery.md"]
---

# Gated Attention

Gated Attention uses a learned gating mechanism to dynamically route between different attention configurations or experts.

## How It Works

A small "gating network" predicts weights for combining different attention modes:

1. Compute multiple attention patterns
2. Gating network predicts combination weights
3. Weighted sum of attention outputs

## Characteristics

- **Dynamic routing**: Not fixed routing like MoE
- **Different from MoE**: Gated attention routes between attention modes, not just expert outputs
- **Combined with MoE**: Often used with expert mixtures

## Used By

- Qwen3 Next: Uses gated attention for hybrid DeltaNet/GQA
- Arcee AI Trinity Large: Combines with coarse-grained MoE

## Related Concepts

- [MoE](./mixture_of_experts.md) - Expert routing
- [Hybrid Attention](./hybrid_attention.md) - Combined architectures

---

## Source

- [LLM Architecture Gallery](../sources/llm_architecture_gallery.md)