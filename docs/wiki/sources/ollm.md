---
title: "oLLM - Large-Context LLM Inference"
type: "source"
category: "AI_Fundamental"
tags: ["llm", "inference", "gpu", "local", "large-context"]
created: "2026-04-22"
updated: "2026-04-22"
sources: ["raw/ollm.md"]
related_topics: ["topics/llm.md", "topics/llm_inference.md"]
---

# oLLM - Large-Context LLM Inference

- **Organization**: Mega4alik
- **Stars**: 2,365
- **License**: MIT

## Overview

oLLM is a lightweight Python library for large-context LLM inference, built on top of Huggingface Transformers and PyTorch. Enables running models on 100k context using ~$200 consumer GPU with 8GB VRAM.

## Key Features

- **Large context**: Up to 100k tokens
- **Consumer GPU friendly**: ~8GB VRAM
- **No quantization**: fp16/bf16 precision only
- **Multiple model support**: gpt-oss-20B, qwen3-next-80B, Llama-3.1-8B-Instruct

## Installation

```bash
pip install --no-build-isolation ollm

# From source
git clone https://github.com/Mega4alik/ollm.git
cd ollm
pip install --no-build-isolation -e .

# For Nvidia GPUs with cuda (optional)
pip install kvikio-cu12  # speeds up inference
```

## System Requirements

- Python
- GPU with 8GB+ VRAM
- Huggingface Transformers
- PyTorch

## Related Topics

- [Generative AI and LLM](../topics/llm.md)
- [Building AI Applications](../topics/Building_AI_applications.md)

---

## Source

- [Raw Source](../../raw/ollm.md)
- [GitHub](https://github.com/Mega4alik/ollm)