---
title: "TurboQuant: 3-bit KV Cache with Near 0 Accuracy Loss"
type: "source"
category: "AI_Fundamental"
tags: ["kv-cache", "quantization", "llm", "inference", "optimization"]
created: "2026-04-14"
updated: "2026-04-14"
sources: ["https://arxiv.org/abs/2504.19874", "https://kaitchup.substack.com/p/turboquant-3-bit-kv-cache-with-near"]
---

# TurboQuant: ~3-bit KV Cache with Near 0 Accuracy Loss?

## Tổng quan

TurboQuant là paper về KV cache quantization cho LLM inference, được popularize bởi Google blog post. Phương pháp này sử dụng fixed random orthogonal rotation để biến KV vectors thành dạng dễ quantize hơn, sau đó lưu trữ với ~3 bits per channel mà không gây degradation đáng kể về chất lượng.

**Paper:** [arXiv:2504.19874](https://arxiv.org/abs/2504.19874) (Apr 2025)
**Authors:** Amir Zandieh, Majid Daliri, Majid Hadian, Vahab Mirrokni (Google Research)

## Vấn đề

KV cache grow tuyến tính với sequence length, trở thành bottleneck cho cả memory capacity và memory bandwidth:
- Memory usage cao
- Decoding bị giới hạn bởi memory bandwidth
- Với large models và long sequences, KV cache có thể limit hơn cả model weights

## Giải pháp: TurboQuant

### Core Idea
1. **Apply fixed random orthogonal rotation** để biến KV vectors thành dạng dễ quantize
2. **Quantize** mỗi rotated coordinate thành nearest value trong precomputed codebook
3. **Reconstruct** bằng centroid lookup + inverse rotation

### Tại sao nó hiệu quả?
- Sau rotation, high-dimensional unit vectors có coordinates **uniform hơn, gần independent hơn**
- Coordinates tập trung quanh zero và behave như Gaussian variables
- **Một single fixed scalar codebook** có thể work well across many KV vectors **không cần calibration**

### Two-stage approach

1. **TurboQuant_mse**: MSE-optimized quantization (cho vector reconstruction)
2. **TurboQuant_prod** (optional): Thêm 1-bit QJL sketch của residual error để reduce inner-product bias trong attention scores

## Performance

| Bits per channel | Quality |
|------------------|---------|
| 3.5 bits | Absolute quality neutrality |
| 2.5 bits | Marginal quality degradation |

### vLLM Integration
- PR [#38479](https://github.com/vllm-project/vllm/pull/38479)
- Configurations:
  - `tq3`: 2-bit keys, 4-bit values (~3-bit average)
  - `tq4`: 3-bit MSE (unstable at time of test)
- With `tq3`: Qwen3.5-27B fits **8 sequences** instead of 2 on 96GB GPU

### llama.cpp
- Partially available (paid content của Kaitchup)

## Evaluation Results (Kaitchup)

Benchmark trên **HumanEval** và **GPQA Diamond**:
- Không thấy degradation đáng kể
- Đặc biệt ấn tượng với GPQA Diamond (đòi hỏi long reasoning traces)

## Nguồn

- [arXiv Paper](https://arxiv.org/abs/2504.19874)
- [Google Research Blog](https://research.google/blog/turboquant-redefining-ai-efficiency-with-extreme-compression/)
- [Kaitchup Substack](https://kaitchup.substack.com/p/turboquant-3-bit-kv-cache-with-near)

## Liên kết liên quan

- [Building AI applications](../topics/Building_AI_applications.md) – LLM inference optimization
