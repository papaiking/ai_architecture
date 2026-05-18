---
title: "AI Fundamental"
type: "topic"
category: "AI_Fundamental"
tags: ["ai-fundamental", "llm", "models", "foundation"]
created: "2026-04-17"
updated: "2026-05-14"
sources: ["sources/llm_finetuning_techniques.md", "sources/vllm_omni.md", "sources/deepeval.md"]
---

# Generative AI and LLM

Kiến thức nền tảng về AI, Generative AI, LLM models, foundation models.

## Core Concepts

- **Tokenization**: Byte-Pair Encoding (BPE).
- **Transformer Architecture**: Attention mechanism, Multi-head attention, Feedforward networks, Normalization.
- **MoE (Mixture-of-Experts)**: Kiến trúc MoE.
- **Quantization**: Kỹ thuật giảm độ chính xác để tối ưu hóa tài nguyên.
- **Embedding**: Giảm chiều dữ liệu, các mô hình embedding (multilingual-e5-large, BAAI/bge-m3).


## Tokenization

## Transformer Architecture

## MoE (Mixture-of-Experts)

## Quantization

## Embedding

## LLM Models

- [MedGemma](../sources/medgemma.md) - Medical AI (Gemma 3 variants)
- [Poolside Laguna](../sources/poolside_laguna.md) - Open source coding model (Apache 2.0)

## Running LLM Model

- [72 Techniques to Optimize LLMs](../sources/llm_optimization_72_techniques.md) - Production optimization techniques map
- [TurboQuant - KV Cache Quantization](../sources/turboquant.md) - 3-bit KV cache with near 0 accuracy loss
- [OptiLLM](../sources/optillm.md) - Optimizing inference proxy: 20+ techniques for 2-10x LLM reasoning accuracy improvement
- [vLLM-Omni](../sources/vllm_omni.md) - Omni-modality inference & serving: text, image, video, audio (4.7k stars)

## Fine tunning model

- [Top 5 LLM Fine-Tuning Techniques](../sources/llm_finetuning_techniques.md) - LoRA, LoRA-FA, VeRA, Delta-LoRA, LoRA+ explained with visuals

## Model evaluation

- [DeepEval](../sources/deepeval.md) - LLM evaluation framework: 30+ metrics for agentic, RAG, multi-turn, MCP, multimodal evals (15.4k stars)
