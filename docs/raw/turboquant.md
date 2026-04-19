# TurboQuant - KV Cache Quantization

**Source**: https://github.com/0xSero/turboquant

## Overview

TurboQuant: Near-optimal KV cache quantization for LLM inference (3-bit keys, 2-bit values) with Triton kernels + vLLM integration.

## Details

- **Org**: 0xSero
- **Stars**: ~1k
- **Paper**: ICLR 2026, arXiv:2504.19874
- **License**: GPL-3.0

## Key Features

- 3-bit keys, 2-bit values compression
- Random orthogonal rotation
- Lloyd-Max optimal scalar quantization
- QJL projection for residual sign bits
- vLLM integration

## Architecture

1. Random orthogonal rotation to spread information
2. Lloyd-Max optimal quantization on Beta-distributed values
3. QJL projection for residual sign bits
4. Group quantization for values

## Usage

```bash
pip install -e .
python validate_paper.py  # Run paper validation
```

---

*Accessed: 2026-04-18*