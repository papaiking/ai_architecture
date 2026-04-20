---
title: "Classification by combining to Internet RAG"
type: "concept"
category: "AI_Fundamental"
tags: ["classification", "rag", "multimodal", "segmentation", "knowledge-cutoff"]
created: "2026-04-20"
updated: "2026-04-20"
---

# Classification by combining to Internet RAG

## Bối cảnh

Các mô hình segmentation dựa trên multimodal LLM như **LISA, SESAME, READ** có thể làm "reasoning segmentation" - ví dụ: "Hãy segment người sáng lập SpaceX" nhờ kiến thức có sẵn trong LLM.

## Vấn đề: Knowledge Cutoff

| Vấn đề | Giải thích |
|---------|-------------|
| **Knowledge Cutoff** | LLM có kiến thức cố định tại thời điểm training |
| **Retraining tốn kém** | Huấn luyện lại toàn bộ model rất tốn ресурс |
| **Novel entities** | Thực thể mới sau cutoff (iPhone 17 Pro Max) |
| **Emerging entities** | Thực thể đang thay đổi (Tổng thống Mỹ hiện tại) |

## Giải pháp: Internet-Augmented RAG

### Cách hoạt động

1. **Query web** - Trong quá trình inference, model gửi query tìm kiếm
2. **Retrieve information** - Lấy thông tin mới nhất từ web
3. **Augment context** - Bổ sung thông tin vào context của LLM
4. **Generate response** - Model có kiến thức cập nhật để segment chính xác

### Lợi ích

- ✅ Khắc phục knowledge cutoff
- ✅ Không cần retrain
- ✅ Có thông tin thời gian thực
- ✅ Áp dụng được cho các thực thể mới

## Related Sources

- [Segmentation with Internet-Augmented Multimodal LLMs](../sources/segmentation_internet_rag.md)

---

## Liên kết liên quan

- [AI Landscape](../topics/ai_landscape.md)