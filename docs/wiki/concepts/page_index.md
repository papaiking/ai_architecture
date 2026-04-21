---
title: "PageIndex"
type: "concept"
category: "Building_AI_applications"
tags: ["rag", "vectorless", "tree-index", "document-navigation", "reasoning"]
created: "2026-04-20"
updated: "2026-04-20"
sources: ["sources/proxy_pointer_rag.md"]
---

# PageIndex

**Vectorless retrieval** - Reasoning-based document navigation thay vì similarity search bằng embedding.

## Core Idea

Thay vì chunk + vector search, PageIndex biến tài liệu thành **cây phân cấp** (tree index) để LLM điều hướng và truy xuất thông tin giống cách con người đọc tài liệu dài.

> "Biến bài toán 'tìm đoạn giống nhất bằng vector' thành 'điều hướng tài liệu bằng suy luận'."

## Cấu trúc Tree Index

```
Root: Toàn bộ tài liệu
├── Chapter 1 (Node cấp 1)
│   ├── Section 1.1 (Node cấp 2)
│   │   └── Pages 1-3 (Node lá)
│   └── Section 1.2
│       └── Pages 4-7
├── Chapter 2
│   └── ...
```

Mỗi node chứa:
- **Span**: nhóm trang/đoạn của tài liệu
- **Metadata**: tiêu đề, page range, mô tả tóm tắt

## Retrieval Process (Reasoning-based)

1. **Đọc overview**: LLM xem root và các node con cấp cao
2. **Chọn đường đi**: LLM quyết định nên vào chapter/section nào
3. **Drill down**: Lặp lại tại mỗi node, chọn child node hứa hẹn nhất
4. **Đọc nội dung thật**: Lấy text thực sự và trả lời query

## So sánh

| Vector RAG | PageIndex |
|-----------|-----------|
| Google search theo từ khóa + similarity | Mở sách, đọc mục lục, chọn chương |
| Fast, cheap | Chi phí LLM cao |
| Similarity search sai chỗ | Reasoning-based, ít hallucination |

## Ưu điểm

- **Giữ nguyên cấu trúc tài liệu**: Mối quan hệ chapter/mục được bảo toàn
- **Bớt lỗi similarity**: LLM reasoning dựa trên mục lục ít bị lôi nhầm
- **Phù hợp domain khó**: Tài liệu kỹ thuật, spec, policy, manual dài

## Hạn chế

- **Chi phí LLM cao**: Cần nhiều LLM calls cho build và retrieval
- **Khó scale**: Lượng query lớn trở thành bottleneck
- **Phức tạp**: Cần implement workflow tree search, fallback, caching

## Khi nào nên dùng?

- Tài liệu rất dài, rất quan trọng (spec, RFC, policy)
- Chất lượng trả lời quan trọng hơn chi phí
- Muốn reasoning-based retrieval hơn là semantic similarity

## Related Documents

- [Proxy-Pointer RAG](../sources/proxy_pointer_rag.md) - Phương pháp "nhái" độ chính xác của PageIndex với vector RAG scale và cost
- [Proxy-Pointer RAG (Concept)](./proxy_pointer_rag.md)
- [Chunking Document](../topics/chunking_document.md)

---

## Source

- Concept based on document navigation and tree-index retrieval research