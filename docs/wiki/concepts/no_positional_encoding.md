---
title: "NoPE - No Positional Encoding"
type: "concept"
category: "AI_Fundamental"
tags: ["position", "encoding", "transformer"]
created: "2026-04-22"
updated: "2026-04-22"
sources: ["sources/llm_architecture_gallery.md"]
---

# NoPE - No Positional Encoding

NoPE is a technique that removes explicit positional encodings from certain transformer layers to test if position can be learned implicitly.

## How It Works

Standard transformer uses positional encodings (sinusoidal or RoPE) to add position information. NoPE layers simply remove this, relying on the attention mechanism to learn position implicitly through other signals.

## Characteristics

- **Implicit position**: Model learns position from context
- **Efficiency**: Saves embedding dimension
- **Experimental**: Not proven universally better

## Selective Application

NoPE is typically used selectively:
- SmolLM3: Every 4th layer uses NoPE
- Kimi K2: MLA layers use NoPE
- Arcee AI Trinity: RoPE + NoPE mixed

## Used By

- SmolLM3
- Kimi K2
- Kimi Linear
- Arcee AI Trinity Large

## Related Concepts

- [RoPE](./rope.md) - Rotary Position Embedding (common alternative)
- [MLA](./multi_latent_attention.md) - Often combined

---

## Source

- [LLM Architecture Gallery](../sources/llm_architecture_gallery.md)