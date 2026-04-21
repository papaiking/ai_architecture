---
title: "Document Tree Index"
type: "concept"
category: "Building_AI_applications"
tags: ["tree-index", "document", "parsing", "dom", "heading"]
created: "2026-04-20"
updated: "2026-04-20"
sources: ["sources/proxy_pointer_rag.md"]
---

# Document Tree Index

Xây tree index cho tài liệu/web bằng cách khai thác cấu trúc có sẵn (title, heading, DOM) + heuristic, chưa cần LLM ở vòng đầu.

## Bước 1: Lấy cấu trúc thô

### Với HTML/web page

Parse DOM, lấy:
- `<title>` → tiêu đề chính
- `<h1>…h6>` → các cấp node
- `<p>`, `<ul>`, `<table>`, `<code>`… → nội dung "lá"

### Với Markdown

Dùng pattern heading (#, ##, ###…) để xác định cấp.

> Coi mỗi heading là một node, các đoạn text giữa hai heading cùng cấp là nội dung.

```
# A
  intro...
## A.1
  content...
## A.2
  content...
# B
  ...
→ Cây: root → A → (A.1, A.2), root → B
```

## Bước 2: Xác định cấp độ và build cây

**Quy tắc:**
- H1 → level 1 (gần root)
- H2 → con của H1 gần nhất trước đó
- H3 → con của H2 gần nhất... tương tự đến H6

**Thuật toán:**
1. Duyệt DOM từ trên xuống
2. Gặp heading mới: tạo node với level = số (1–6)
3. Dùng stack để tìm "cha" gần nhất có level < current_level
4. Thêm node này vào children của cha
5. Nội dung (p, ul, code…) nằm sau heading được gán vào node.content

```python
class Node:
    id
    level
    title
    content_text
    children: List[Node]
```

## Bước 3: Chuẩn hóa các "lá" (span/page)

Mỗi node không nên quá to. Chia nhỏ section thành các sub-node "page":

- Chia theo số token (400–800 token mỗi "page")
- Vẫn gắn là children của node section đó

**Cây có 2–3 tầng:**
1. Tầng heading (H1–H3): thể hiện logic tài liệu
2. Tầng lá: các "page" tập hợp vài đoạn liên tiếp, dùng để feed LLM

## Bước 4: Thêm metadata

Với mỗi node, lưu:
- **path** (breadcrumb): "Doc title > Section A > Subsection A.1"
- **page_range** hoặc offset trong file gốc
- **summary** ngắn 1–3 câu: có thể sinh bằng LLM cho node cấp cao

Cho web page đơn giản: title + heading + path đã đủ để LLM "định vị" tốt.

## Bước 5: Lưu trữ

- **JSON**: trong DB hoặc file, mỗi node có id, parent_id, children_ids
- **DB quan hệ**: bảng nodes với các cột id, parent_id, level, title, content, path, order

Không cần vector DB; tree index là graph/cây thuần dữ liệu text + metadata.

## Bước 6: Sử dụng khi truy vấn

**Bước 1**: Lấy node cấp cao (H1/H2) + summary/path → LLM hỏi "Với Q, nên xem phần nào?" → LLM trả id node phù hợp

**Bước 2**: Với node đó, lặp lại với children (H3 hoặc "page") để khoanh dần

**Bước 3**: Khi đến lá, lấy content_text của 1–3 lá liên tiếp → LLM trả lời

## Related Documents

- [Proxy-Pointer RAG](./proxy_pointer_rag.md)
- [Proxy-Pointer RAG (Source)](../sources/proxy_pointer_rag.md)
- [PageIndex](./page_index.md) - Phương pháp "vectorless" gốc

---

## Source

- Concept based on document parsing and tree-index retrieval research