---
title: "Proxy-Pointer RAG: Achieving Vectorless Accuracy at Vector RAG Scale and Cost"
type: "source"
category: "AI_Fundamental"
tags: ["rag", "vector", "search", "proxy", "pointer", "retrieval"]
created: "2026-04-20"
updated: "2026-04-20"
sources: ["raw/proxy_pointer_rag.md"]
related_topics: ["topics/ai_landscape.md", "topics/chunking_document.md"]
related_concepts: ["concepts/page_index.md", "concepts/proxy_pointer_rag.md"]
---

# Proxy-Pointer RAG: Achieving Vectorless Accuracy at Vector RAG Scale and Cost

- **Author**: VNG

## Overview

Paper giới thiệu Proxy-Pointer RAG - phương pháp mới để đạt độ chính xác như vector search mà không cần vector database, với chi phí và scale như sparse retrieval.

## Vector RAG Problems

- **Embedding Mismatch**: Query và document embedding ở different semantic spaces
- **Index Drift**: Documents thay đổi nhưng index không cập nhật
- **Scaling Cost**: Vector search tốn kém ở scale hàng triệu documents
- **Metadata Overhead**: Cần lưu cả embedding và metadata

## Solution: Proxy-Pointer RAG

Thay vì embedding, sử dụng **pointer-based proxy**:

1. **Sparse Retrieval**: BM25 hoặc SPLADE cho candidate ban đầu
2. **Proxy Classification**: LLM classify candidate có liên quan
3. **Proxy Refinement**: LLM extract chính xác passage cần thiết

## Kết quả

- **Vectorless accuracy** - chính xác như dense vector search
- **Vector RAG scale** - scale được như sparse retrieval
- **Giảm cost đáng kể** so với vector search truyền thốngi

## Ứng dụng

- RAG systems cần scale lớn
- Hệ thống cần giảm chi phí infrastructure

---

## Related Topics

- [AI Landscape](../topics/ai_landscape.md)

---

## Source

- [Raw Source](../../raw/proxy_pointer_rag.md)
- [PDF](../../raw/Proxy-Pointer%20RAG_%20Achieving%20Vectorless%20Accuracy%20at%20Vector%20RAG%20Scale%20and%20Cost.pdf)