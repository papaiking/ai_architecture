---
title: "MoE - Mixture of Experts"
type: "concept"
category: "AI_Fundamental"
tags: ["moe", "routing", "sparse"]
created: "2026-04-22"
updated: "2026-04-22"
sources: ["sources/llm_architecture_gallery.md"]
---

# MoE - Mixture of Experts

Mixture of Experts (MoE) enables large models by routing each token to a subset of parameters instead of activating all parameters for every token.

## How It Works

Each layer has multiple "expert" networks. A gating mechanism (typically top-k) selects which experts process each token:

- Only selected experts compute
- Rest of experts remain inactive
- Total parameters can be huge, but active parameters are smaller

## Key Metrics

| Model | Total Params | Active Params | % Active |
|-------|-------------|--------------|----------|
| DeepSeek V3 | 671B | 37B | 5.5% |
| Llama 4 Maverick | 400B | 17B | 4.3% |
| Qwen3 | 235B | 22B | 9.4% |
| GLM-5 | 744B | 40B | 5.4% |

## Characteristics

- **Massive scale**: Enables trillion-parameter models
- **Sparse activation**: Only subset active per token
- **Expert selection**: Top-k routing (usually k=1-2)
- **Shared experts**: Some experts always active

## Architecture Variations

- **Standard MoE**: Simple top-k routing
- **Hybrid MoE**: Combines transformer with state space models
- **Coarse-grained**: Fewer, larger experts
- **Fine-grained**: More, smaller experts
- **Latent MoE**: Routing in latent space

## Used By

- DeepSeek V3 / V3.2 / R1
- Llama 4 Maverick
- Qwen3 series
- GPT-OSS
- Mistral Large 3
- GLM-4.5 / 4.7 / 5

## Related Concepts

- [Gated Attention](./gated_attention.md) - Learned gating
- [Hybrid Attention](./hybrid_attention.md) - Combined with SSMs

---

## Source

- [LLM Architecture Gallery](../sources/llm_architecture_gallery.md)