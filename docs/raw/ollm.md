# oLLM - Large-Context LLM Inference

**Organization**: Mega4alik
**Stars**: 2,365
**License**: MIT

## Overview

oLLM is a lightweight Python library for large-context LLM inference, built on top of Huggingface Transformers and PyTorch. It enables running models like gpt-oss-20B, qwen3-next-80B, or Llama-3.1-8B-Instruct on 100k context using ~$200 consumer GPU with 8GB VRAM. No quantization is used—only fp16/bf16 precision.

## Key Features

- **Large context**: Supports up to 100k token context
- **Consumer GPU friendly**: Runs on ~$200 GPU with 8GB VRAM
- **No quantization**: Uses fp16/bf16 precision only
- **Multiple model support**: gpt-oss-20B, qwen3-next-80B, Llama-3.1-8B-Instruct, and more

## Installation

```bash
pip install --no-build-isolation ollm

# From source
git clone https://github.com/Mega4alik/ollm.git
cd ollm
pip install --no-build-isolation -e .

# For Nvidia GPUs with cuda (optional, speeds up inference)
pip install kvikio-cu{cuda_version}  # e.g., kvikio-cu12
```

## System Requirements

- Python
- GPU with 8GB+ VRAM
- Huggingface Transformers
- PyTorch

---

**Source**: [GitHub](https://github.com/Mega4alik/ollm)
**Date**: 2026-04-22