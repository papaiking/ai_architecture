---
title: "OptiLLM"
type: "source"
category: "AI_Fundamental"
tags: ["llm-inference", "optimization", "reasoning", "proxy", "openai-compatible"]
created: "2026-05-12"
updated: "2026-05-12"
related_topics: ["topics/llm.md"]
---

# OptiLLM

- **Type**: LLM Inference Optimization Proxy
- **Slogan**: Optimizing inference proxy for LLMs

![OptiLLM Logo](../media/optillm_logo.png)

OpenAI API-compatible optimizing inference proxy that implements 20+ state-of-the-art techniques to dramatically improve LLM accuracy and performance on reasoning tasks — without requiring any model training or fine-tuning.

## Details

- **Org**: algorithmicsuperintelligence
- **License**: Apache-2.0
- **GitHub**: [https://github.com/algorithmicsuperintelligence/optillm](https://github.com/algorithmicsuperintelligence/optillm)
- **Stars**: 3.6k+
- **PyPI**: [optillm](https://pypi.org/project/optillm/)
- **HuggingFace Space**: [optillm](https://huggingface.co/spaces/codelion/optillm)
- **Colab Demo**: [Open in Colab](https://colab.research.google.com/drive/1SpuUb8d9xAoTh32M-9wJsB50AOH54EaH?usp=sharing)

## Key Features

- **2-10x Accuracy Improvement** on math, coding, and logical reasoning tasks
- **Drop-in Replacement** — Works with any OpenAI-compatible API endpoint
- **20+ Optimization Techniques** — From simple Best-of-N to advanced MCTS and planning
- **Zero Training Required** — Just proxy existing API calls through OptiLLM
- **Multi-Provider** — Supports OpenAI, Anthropic, Google, Cerebras, 100+ models via LiteLLM
- **Production Ready** — Used in production by companies and researchers worldwide

## Optimization Techniques

| Technique | Slug | Description |
|-----------|------|-------------|
| **MARS** | `mars` | Multi-agent reasoning with diverse temperature exploration & cross-verification |
| **CePO** | `cepo` | Cerebras Planning & Optimization: Best of N + CoT + Self-Reflection |
| **CoT with Reflection** | `cot_reflection` | Chain-of-thought with `<thinking>`, `<reflection>`, `<output>` sections |
| **PlanSearch** | `plansearch` | Search algorithm over candidate plans for problem-solving |
| **ReRead** | `re2` | Improves reasoning by processing queries twice |
| **Self-Consistency** | `self_consistency` | Advanced self-consistency method |
| **Z3 Solver** | `z3` | Utilizes Z3 theorem prover for logical reasoning |
| **R\* Algorithm** | `rstar` | R\* algorithm for problem-solving |
| **LEAP** | `leap` | Learns task-specific principles from few-shot examples |
| **Round Trip Optimization** | `rto` | Optimizes responses through round-trip process |
| **Best of N Sampling** | `bon` | Generates N responses and selects the best |
| **Mixture of Agents** | `moa` | Combines responses from multiple critiques |
| **Monte Carlo Tree Search** | `mcts` | MCTS for decision-making in chat responses |
| **PV Game** | `pvg` | Prover-verifier game at inference time |
| **AutoThink** | N/A | Query complexity classification + steering vectors |
| **Deep Confidence** | N/A | Confidence-guided reasoning with multiple intensity levels |
| **CoT Decoding** | N/A | Chain-of-thought decoding without explicit prompting |
| **Entropy Decoding** | N/A | Adaptive sampling based on token uncertainty |

## Plugins

- **System Prompt Learning (SPL)** — Model acquires program solving knowledge (Karpathy's "third paradigm")
- **Deep Think** — Gemini-like Deep Think using inference time scaling for reasoning LLMs
- **Long-Context CePO (LongCePO)** — Planning + divide-and-conquer for infinite context processing
- **MCP Client** — Model Context Protocol client for external tools/files/resources
- **Router** — Routes requests to different approaches based on prompt using optillm-modernbert-large
- **Memory** — Short-term memory for unbounded context length with any LLM
- **Privacy** — Anonymize PII in requests and deanonymize in responses
- **Web Search** — Google searches via Chrome automation (Selenium)
- **Deep Research** — Test-Time Diffusion Deep Researcher (TTD-DR) for comprehensive reports
- **Proxy** — Load balancing and failover across multiple LLM providers

## Proven Results

| Technique | Base Model | Improvement | Benchmark |
|-----------|------------|-------------|-----------|
| MARS | Gemini 2.5 Flash Lite | **+30.0 points** | AIME 2025 (43.3→73.3) |
| CePO | Llama 3.3 70B | **+18.6 points** | Math-L5 (51.0→69.6) |
| AutoThink | DeepSeek-R1-1.5B | **+9.34 points** | GPQA-Diamond |
| LongCePO | Llama 3.3 70B | **+13.6 points** | InfiniteBench |
| MOA | GPT-4o-mini | **Matches GPT-4** | Arena-Hard-Auto |
| PlanSearch | GPT-4o-mini | **+20% pass@5** | LiveCodeBench |

## Quick Start

```bash
# Install
pip install optillm

# Start server
export OPENAI_API_KEY="your-key-here"
optillm

# Use with any OpenAI client
# Just prepend technique slug to model name:
# model="moa-gpt-4o-mini" gives GPT-4o performance from GPT-4o-mini
```

## Docker

```bash
docker pull ghcr.io/algorithmicsuperintelligence/optillm:latest
docker run -p 8000:8000 ghcr.io/algorithmicsuperintelligence/optillm:latest
```

## Local Inference

OptiLLM supports loading any HuggingFace model or LoRA directly. Supports logprobs, CoT decoding, and entropy decoding.

---

## Source

- [Raw Source](../../raw/optillm_20260512.md)
- [GitHub Repository](https://github.com/algorithmicsuperintelligence/optillm)
- [PyPI](https://pypi.org/project/optillm/)

## Related Topics

- [Generative AI and LLM](../topics/llm.md) — Running LLM Model section
