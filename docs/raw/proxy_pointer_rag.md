---
title: "Proxy-Pointer RAG: Achieving Vectorless Accuracy at Vector RAG Scale and Cost"
type: "source"
category: "AI_Fundamental"
tags: ["rag", "vector", "search", "proxy", "pointer", "retrieval"]
created: "2026-04-20"
updated: "2026-04-20"
sources: ["raw/Proxy-Pointer RAG_ Achieving Vectorless Accuracy at Vector RAG Scale and Cost.pdf"]
---

# Proxy-Pointer RAG: Achieving Vectorless Accuracy at Vector RAG Scale and Cost

**Author**: VNG
**Type**: Research Paper

## Tổng quan

Paper giới thiệu Proxy-Pointer RAG - phương pháp mới để đạt độ chính xác như vector search mà không cần vector database, với chi phí và scale như sparse retrieval.

## Vấn đề với Vector RAG hiện tại

- **Embedding Mismatch": Query và document embedding có thể khác nhau về semantic space
- **Index Drift": Document thay đổi nhưng index không cập nhật
- **Scaling Cost": Vector search tốn kém khi scale lên hàng triệu documents
- **Metadata Overhead": Cần lưu trữ cả embedding và metadata

## Giải pháp Proxy-Pointer RAG

Sử dụng **pointer-based proxy** thay vì embedding:

1. **Sparse Retrieval**: Dùng BM25 hoặc SPLADE để retrieve candidate ban đầu
2. **Proxy Classification": Dùng LLM để classify candidate có liên quan không
3. **Proxy Refinement**: Cuối cùng dùng LLM để extract chính xác passage cần thiết

## Kết quả

- Đạt **vectorless accuracy** - chính xác như dense vector search
- Giữ được **vector RAG scale** - scale được như sparse retrieval
- Giảm **cost đáng kể** so với vector search truyền thốngi

## Ứng dụng

- RAG systems cần scale lớn
- Hệ thống cần giảm chi phí infrastructure
- Nơi mà embedding quality không ổn định

---

## Source

- [PDF](./Proxy-Pointer%20RAG_%20Achieving%20Vectorless%20Accuracy%20at%20Vector%20RAG%20Scale%20and%20Cost.pdf)