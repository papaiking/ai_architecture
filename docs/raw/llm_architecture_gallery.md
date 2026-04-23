# LLM Architecture Gallery

**Author**: Sebastian Raschka, PhD
**Website**: https://sebastianraschka.com/llm-architecture-gallery/
**Last Updated**: April 10, 2026

This page collects architecture figures and fact sheets from posts on Sebastian Raschka's blog, plus selected release posts or technical reports when a new architecture has not been covered there yet.

## Overview

The LLM Architecture Gallery is a comprehensive collection of LLM architecture factsheets covering various models. It includes:
- Architecture figures and fact sheets
- Comparison tools to compare two architectures side by side
- AA Intelligence Index scores
- KV cache calculations

## Models Included

The gallery covers 70+ LLM architectures including:

### Dense Models
- GPT-2 XL (1.5B) - 2019-11-05
- Llama 3 (8B) - 2024-04-18
- Llama 3.2 (1B) - 2024-09-25
- OLMo 2 (7B) - 2024-11-25
- Gemma 3 (27B) - 2025-03-11
- Mistral Small 3.1 (24B) - 2025-03-18
- Qwen3 (32B) - 2025-04-28
- Qwen3 (4B) - 2025-04-28
- Qwen3 (8B) - 2025-04-28
- SmolLM3 (3B) - 2025-06-19
- GPT-OSS (120B) - 2025-08-04
- GPT-OSS (20B) - 2025-08-04
- Gemma 3 (270M) - 2025-08-14
- OLMo 3 (32B) - 2025-11-20
- OLMo 3 (7B) - 2025-11-20
- Gemma 4 (31B) - 2026-03-11

### MoE Models
- DeepSeek V3 (671B) - 2024-12-26
- DeepSeek R1 (671B) - 2025-01-20
- Llama 4 Maverick (400B) - 2025-04-05
- Qwen3 (235B-A22B) - 2025-04-28
- Kimi K2 (1T) - 2025-07-10
- GLM-4.5 (355B) - 2025-07-28
- Grok 2.5 (270B) - 2025-08-22
- Qwen3 Next (80B-A3B) - 2025-09-09
- MiniMax M2 (230B) - 2025-10-23
- Kimi Linear (48B-A3B) - 2025-10-30
- DeepSeek V3.2 (671B) - 2025-12-01
- Mistral Large 3 (673B) - 2025-12-02
- Nemotron 3 Nano (30B-A3B) - 2025-12-04
- Xiaomi MiMo-V2-Flash (309B) - 2025-12-16
- GLM-4.7 (355B) - 2025-12-22
- Arcee AI Trinity Large (400B) - 2026-01-27
- GLM-5 (744B) - 2026-02-11
- Nemotron 3 Super (120B-A12B) - 2026-03-11

## Key Architecture Concepts

### Attention Mechanisms
- **MHA** (Multi-Head Attention): Classic full attention
- **GQA** (Grouped-Query Attention): Shares KV heads across query groups
- **MLA** (Multi-Latent Attention): DeepSeek's latent KV attention
- **SWA** (Sliding-Window Attention): Local context attention
- **QK-Norm**: Query/Key normalization for training stability
- **NoPE** (No Positional Encoding): Removes positional embeddings in some layers

### MoE (Mixture of Experts)
- Sparse MoE: Routes to subset of experts per token
- Hybrid MoE: Combines transformer with state space models
- Gated Attention: Learned gating mechanism
- Latent MoE: Latent space routing

### Architecture Patterns
- Pre-norm vs Post-norm
- Dense vs Sparse
- Shared experts
- Alternating attention (local/global)

## Available Resources

- Architecture comparison tool
- KV cache calculations
- AA Intelligence Index scores
- From-scratch implementations
- Config JSON files from HuggingFace
- Technical reports

## Related Links

- [LLMs From Scratch](https://github.com/rasbt/LLMs-from-scratch)
- [Reasoning Models](https://github.com/rasbt/reasoning-from-scratch)
- [Ahead of AI Blog](https://magazine.sebastianraschka.com)

---

**Source**: [LLM Architecture Gallery](https://sebastianraschka.com/llm-architecture-gallery/)
**Date**: 2026-04-22