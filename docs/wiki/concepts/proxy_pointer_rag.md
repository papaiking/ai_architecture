---
title: "Proxy-Pointer RAG"
type: "concept"
category: "Building_AI_applications"
tags: ["rag", "vectorless", "proxy", "pointer", "chunking", "metadata"]
created: "2026-04-20"
updated: "2026-04-20"
sources: ["sources/proxy_pointer_rag.md"]
---

# Proxy-Pointer RAG

Thiết kế lại pipeline RAG để tận dụng cấu trúc tài liệu (mục lục, heading, tree…) mà vẫn giữ chi phí và tốc độ kiểu vector RAG thông thường.

## Bối cảnh: Vấn đề của RAG thường

**RAG phổ biến hiện nay:**

- Cắt tài liệu thành chunk phẳng (không để ý heading/hierarchy)
- Dùng vector DB tìm top-k theo cosine similarity

**Điểm yếu:**

- Dễ lấy trúng chunk "gần đúng" nhưng không đúng phần
- Thiếu continuity: lấy 1 đoạn giữa chương, bỏ mất các đoạn liền kề
- Tài liệu lớn, nhiều phần lồng nhau (spec, RFC) hay fail

## Ý tưởng cốt lõi

Proxy-Pointer RAG cố đạt "độ chính xác cấu trúc" kiểu PageIndex, với chi phí vector RAG. Tách làm hai vai trò:

| Vai trò | Mô tả |
|--------|-------|
| **Proxy** | Vector embedding đại diện cho node/section trong tài liệu |
| **Pointer** | Metadata + breadcrumb để lần ngược và mở rộng đúng bối cảnh |

> Vector dùng để "khoanh vùng", pointer dùng để "mở rộng đúng chỗ".

## Pipeline

### Ingestion (chuẩn bị dữ liệu)

1. **Parse heading/tree**: Dùng regex/HTML parser tạo cây skeleton (root → chapters → sections → subsections)
2. **Section-aware chunking**: Chunk gắn với node cụ thể trong tree, giữ trọn section
3. **Gắn breadcrumb**: "Chapter 2 > Section 2.1 > Subsection: Training pipeline…"
4. **Tạo embedding**: Từ text + breadcrumb → vector "biết" nó thuộc phần nào
5. **Lưu metadata**: id, parent_id, children_ids, index trong section

### Retrieval (lúc query)

1. **Vector search**: Embed Q, search top-k proxies
2. **Pointer expansion**: Dùng metadata để:
   - Lùi về cha/ancestor nếu cần
   - Kéo thêm sibling/neighbor để có context liên tục
3. **Filtering/de-dup/ranking**: Loại chunk lặp, ưu tiên đúng cấp độ phù hợp câu hỏi

## Tại sao "vectorless accuracy at vector cost"?

| Vectorless RAG (PageIndex) | Proxy-Pointer RAG |
|--------------------------|-------------------|
| Dùng LLM để điều hướng tree | Không dùng LLM ở retrieval |
| Rất chính xác nhưng đắt | Chi phí như vector RAG |
| Chậm với lượng query lớn | Scale được như vector RAG |

**Proxy-Pointer RAG:**
- "Thông minh cấu trúc" nằm trong cách chunk, thêm breadcrumb, dùng pointer
- Không tốn thêm LLM call, chỉ là engineering
- Chi phí/scale tương đương vector RAG
- Chất lượng gần với tree-based/LLM-navigation

## Ưu điểm thực tế

- **Dễ thêm vào stack**: LangChain, LlamaIndex… chỉ thêm lớp metadata + logic expansion
- **Không yêu cầu model mới**: Chủ yếu design lại representation và retrieval logic
- **Giữ được độ chính xác cao**: Query yêu cầu reasoning across sections được xử lý tốt

## Related Documents

- [Chunking Document](../topics/chunking_document.md)
- [Document Tree Index](./document_tree_index.md) - Cách build tree từ DOM/heading
- [PageIndex](./page_index.md) - Phương pháp "vectorless" gốc mà Proxy-Pointer RAG tham khảo
- [Proxy-Pointer RAG (Source)](../sources/proxy_pointer_rag.md)

---

## Source

- Concept based on Proxy-Pointer RAG research paper