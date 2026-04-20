---
title: "Segmentation with Internet-Augmented Multimodal LLMs"
type: "source"
category: "AI_Fundamental"
tags: ["segmentation", "multimodal", "rag", "reasoning", "computer-vision"]
created: "2026-04-20"
updated: "2026-04-20"
related_topics: ["topics/ai_landscape.md", "topics/building_ai_applications/ai_applications.md"]
related_concepts: ["concepts/classification_with_internet_rag.md"]
---

# Segmentation with Internet-Augmented Multimodal LLMs

**Type**: Research Paper

[arXiv](https://arxiv.org/abs/2604.14147v1)

## Overview

Các mô hình segmentation dựa trên multimodal LLM như LISA, SESAME, READ có thể làm **"reasoning segmentation"** nhờ kiến thức có sẵn trong LLM.

## Vấn đề

LLM có **knowledge cutoff** cố định và việc huấn luyện lại rất tốn kém. Chúng thường không biết các thực thể mới xuất hiện sau cutoff:

- **iPhone 17 Pro Max** (ra 2025)
- **"Tổng thống Mỹ hiện tại"**

Điều này dẫn đến **thất bại** khi phải segment các thực thể:

| Loại | Ví dụ | Vấn đề |
|------|-------|---------|
| **Novel entities** | iPhone 17 Pro Max | Không có trong training data |
| **Emerging entities** | Tổng thống Mỹ 2026 | Thông tin đã thay đổi sau cutoff |

## Giải pháp

Dùng **Retrieval-Augmented Generation (RAG)** để cho mô hình truy cập **web thời gian thực** trong lúc inference, từ đó khắc phục hạn chế về kiến thức.

## Liên quan

- [Classification by combining to Internet RAG](../concepts/classification_with_internet_rag.md)

---

## Nguồn

- [PDF](../../raw/segmentation_internet_rag.pdf)
- [arXiv](https://arxiv.org/abs/2604.14147v1)

## Liên kết liên quan

- [AI Landscape](../topics/ai_landscape.md)