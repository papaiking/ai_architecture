---
title: "DeepSeek Sparse Attention"
type: "concept"
category: "AI_Fundamental"
tags: ["attention", "deepseek", "sparse"]
created: "2026-04-22"
updated: "2026-04-22"
sources: ["sources/llm_architecture_gallery.md"]
---

# DeepSeek Sparse Attention

DeepSeek Sparse Attention is an evolutionary update to MLA that uses sparse patterns for improved long-context efficiency.

## How It Works

Building on MLA, DeepSeek adds sparse attention patterns:
- **Selective attention**: Some tokens sparsely attended
- **Segment-level**: Attention within segments
- **Global+local**: Hybrid approach

## Characteristics

- **Efficiency-focused**: Reduces long-context costs
- **Evolutionary**: Not new paradigm, but optimization
- **Lower KV cache**: Maintains benefits of MLA

## Used By

- DeepSeek V3.2
- GLM-5

## Related Concepts

- [MLA](./multi_latent_attention.md) - Base architecture
- [SWA](./sliding_window_attention.md) - Alternative sparse approach

---

## Source

- [LLM Architecture Gallery](../sources/llm_architecture_gallery.md)