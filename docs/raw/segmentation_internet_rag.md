---
title: "Segmentation with Internet-Augmented Multimodal LLMs"
type: "source"
category: "AI_Fundamental"
tags: ["segmentation", "multimodal", "rag", "reasoning", "computer-vision"]
created: "2026-04-20"
updated: "2026-04-20"
related_topics: ["topics/ai_landscape.md"]
---

# Segmentation with Internet-Augmented Multimodal LLMs

**Type**: Research Paper

## Overview

Các mô hình segmentation dựa trên multimodal LLM như LISA, SESAME, READ có thể làm "reasoning segmentation" nhờ kiến thức có sẵn trong LLM.

## Vấn đề

LLM có **knowledge cutoff** cố định và việc huấn luyện lại rất tốn kém. Chúng thường không biết các thực thể mới xuất hiện sau cutoff:
- iPhone 17 Pro Max (ra 2025)
- "Tổng thống Mỹ hiện tại"

Điều này dẫn đến **thất bại** khi phải segment các thực thể:
- **Novel entities** - thực thể mới
- **Emerging entities** - thực thể đang diễn biến, cần thông tin cập nhật từ thế giới thực

## Giải pháp

Dùng **Retrieval-Augmented Generation (RAG)** để cho mô hình truy cập web thời gian thực trong lúc inference, từ đó khắc phục hạn chế về kiến thức.

## Related Concepts

- [Classification by combining to Internet RAG](../concepts/classification_with_internet_rag.md)

---

## Nguồn

- [PDF](./segmentation_internet_rag.pdf)
- [arXiv](https://arxiv.org/abs/2604.14147v1)