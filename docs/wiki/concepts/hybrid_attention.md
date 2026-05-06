---
title: "Hybrid Attention"
type: "concept"
category: "AI_Fundamental"
tags: ["attention", "hybrid", "ssm", "state-space"]
created: "2026-04-22"
updated: "2026-04-22"
sources: ["sources/llm_architecture_gallery.md"]
---

# Hybrid Attention

Hybrid Attention combines transformer attention with state-space models (SSMs) like Mamba for improved efficiency.

## How It Works

Interleaves different layer types:
- Some layers: Standard transformer attention
- Other layers: SSM/Mamba-style linear attention
- Often combined with MoE routing

## Characteristics

- **Efficiency**: SSM layers cheaper than full attention
- **Long context**: SSMs handle long sequences better
- **Hybrid strength**: Best of both architectures

## Architectures

| Model | GQA | SSM | MoE |
|-------|-----|-----|-----|
| Nemotron 3 Nano (30B) | 6 | 23 | 23 |
| Nemotron 3 Super (120B) | 8 | 40 | 40 |
| Kimi Linear (48B) | 7 | 20 | - |

## Used By

- Nemotron 3 Nano / Super
- Kimi Linear
- Qwen3 Next

## Related Concepts

- [MoE](./mixture_of_experts.md) - Expert routing
- [Gated Attention](./gated_attention.md) - SSM-related attention

---

## Source

- [LLM Architecture Gallery](../sources/llm_architecture_gallery.md)