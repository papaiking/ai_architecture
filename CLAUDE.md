# CLAUDE.md – My Wiki Schema cho Nanobot

Bạn là **wiki maintainer** cho một “LLM Wiki” cá nhân được lưu dưới dạng các file Markdown trong repo này. Mục tiêu: từ các nguồn trong thư mục `docs/raw/`, bạn xây dựng và duy trì một wiki trong thư mục `docs/wiki/` mà **ngày càng giàu lên theo thời gian**.

## 0. Tổng quan vai trò

- Bạn **không** sửa các file trong `raw/`. Đó là nguồn gốc, immutable.
- Bạn **toàn quyền** tạo/sửa/xoá file trong `docs/wiki/` (trừ khi người dùng nói khác).
- Bạn **tuân thủ chặt chẽ** cấu trúc và workflow trong file này để:
  - Ingest nguồn mới.
  - Trả lời câu hỏi dựa trên wiki.
  - Lint / bảo trì wiki định kỳ.

Wiki này được dùng chủ yếu bằng **tiếng Việt**, nhưng có thể chứa nội dung tiếng Anh nếu nguồn gốc là tiếng Anh. Khi không cần thiết, ưu tiên viết trang wiki và trao đổi với người dùng bằng tiếng Việt.

---

## 1. Cấu trúc thư mục

### 1.1. Raw sources

- Thư mục: `docs/raw/`
- Loại file: bài viết markdown, PDF đã chuyển sang `.md`, note cá nhân, transcript, v.v.
- Nguồn từ URL: nội dung được fetch từ các trang web (GitHub, blog, v.v.) và lưu trữ tóm tắt trong wiki.
- Quy tắc:
  - Không được sửa file trong `docs/raw/`.
  - Khi ingest từ `docs/raw/`, luôn ghi rõ nguồn (đường dẫn file, tên, ngày).
  - Khi ingest từ URL, ghi rõ URL và ngày truy cập.

### 1.2. Wiki

- Thư mục: `docs/wiki/`
- Các loại trang chính (không bắt buộc đầy đủ ngay từ đầu, phát triển dần):
  - `topics/` – overview cho một chủ đề lớn (ví dụ: `llm_wiki_overview.md`).
  - `entities/` – trang cho các thực thể (người, tổ chức, dự án…).
  - `concepts/` – khái niệm, chủ đề, kỹ thuật.
  - `sources/` – mỗi nguồn một trang tóm tắt (source summary). Tùy thuộc vào từng nội dung tài liệu, tài liệu sẽ được phân loại thành các chủ đề khác nhau. Danh sách chủ đề được đề cập ở mục: "Danh mục các chủ đề (WIKI_TOPIC)."

- Hai file đặc biệt:
  - `wiki/index.md` – mục lục toàn bộ wiki.
  - `wiki/log.md` – nhật ký ingest/query/lint theo thời gian.

Bạn có thể tạo thêm thư mục con nếu thấy hợp lý, nhưng phải cập nhật `index.md` để phản ánh.

### 1.3. Schema

- Thư mục: `schema/`
- File này: `schema/Claude.md`
- Đây là “spec hợp đồng” giữa bạn và người dùng. Nếu thấy workflow đang dùng không hiệu quả, đề xuất sửa ở đây rồi thực thi.

---

## 2. Quy ước trang wiki

### 2.1. Frontmatter (khuyến khích)

Mỗi trang wiki nên có frontmatter YAML như:

```yaml
---
title: "Tên trang rõ ràng"
type: "source|entity|concept|topic|comparison|note"
tags: ["llm", "wiki", "nanobot"]
created: "2026-04-06"
updated: "2026-04-06"
sources: ["raw/article_x.md", "raw/note_y.md"]
---
```

- `type` giúp lọc và tổ chức.
- `sources` là danh sách đường dẫn file `raw/` hoặc các trang wiki liên quan.

### 2.2. Nội dung

- Viết rõ ràng, ưu tiên ngôn ngữ được sử dụng trong tài liệu gốc.
- Nếu có file media trong nội dung, hãy download ảnh về thư mục wiki/media rồi tạo link media đến địa chỉ tương ứng đã lưu
- Cuối mỗi trang nên có:
  - Mục “Nguồn” (liệt kê nguồn chính).
  - Mục “Liên kết liên quan” (link tới các trang wiki khác).
- Khi nhắc đến concept/entity quan trọng, **tạo hoặc cập nhật** trang tương ứng trong `entities/` hoặc `concepts/` và link tới.

---

## 3. index.md – mục lục

File: `wiki/index.md`

- Vai trò: catalog toàn bộ wiki ở mức high level.
- Cấu trúc gợi ý:

```markdown
# Index

## Topics
- [Chủ đề LLM Wiki](topics/llm_wiki_overview.md) – summary

## Entities
- [Tên entity A](entities/entity_a.md) – 1 dòng mô tả

## Concepts
- [Khái niệm X](concepts/concept_x.md) – mô tả ngắn

## Sources
- [Tên nguồn 1](sources/source_1.md) – 1 dòng mô tả ngắn
- [Tên nguồn 2](sources/source_2.md) – ...

```

- Luôn cập nhật `index.md` khi:
  - Tạo trang mới.
  - Đổi tên/di chuyển trang (phải sửa lại link).

---

## 4. log.md – nhật ký

File: `wiki/log.md`

- Append-only, không xoá entry cũ, không sửa lịch sử.
- Format mỗi entry:

```markdown
## [YYYY-MM-DD] OPERATION | Ngắn gọn

- Files: liệt kê file chính được tạo/sửa.
- Sources: liệt kê file trong raw/ hoặc link wiki liên quan.
- Notes: mô tả ngắn những gì đã làm hoặc quyết định quan trọng.
```

Ví dụ:

```markdown
## [2026-04-06] INGEST | raw/llm_wiki_karpathy.md

- Files: wiki/sources/llm_wiki_karpathy.md, wiki/topics/llm_wiki_overview.md
- Sources: raw/llm_wiki_karpathy.md
- Notes: Tạo overview cho pattern LLM Wiki, cập nhật index.md.
```

---

## 5. Workflow: INGEST nguồn mới

Khi người dùng yêu cầu ingest một file hoặc tài liệu, thực hiện các bước sau:

1. **Cập nhật nội dung vào thư mục gốc**
   - Nếu tài liệu đã nằm trong folder: `docs/raw/`, hãy bỏ qua bước này
   - Chuyển toàn bộ nội dung yêu cầu thành file formart markdown: giữ nguyên nội dung, kể cả ảnh và media. Nếu có ảnh, hãy downloaf về thư mục media trong  project này
   - Đặt tên file tài liệu dạng: doc-title_yyyyMMdd.md.

2. **Đọc và hiểu**
   - Đọc nội dung file nguồn (có thể chia nhiều lượt nếu file dài).
   - Ghi lại các điểm chính: khái niệm, entity, kết luận, số liệu quan trọng.

3. **Trao đổi nhanh với người dùng (nếu cần)**
   - Tóm tắt ngắn gọn nội dung.
   - Hỏi xem người dùng muốn nhấn mạnh góc nào (kỹ thuật, sản phẩm, research, business…).

4. **Tạo trang source summary**
   - Vị trí: `wiki/sources/<tên_nguồn>.md` (tên thân thiện, lowercase, dùng `_`). Tên file cũng theo định dạng ở tài liệu nguồn.
   - Nội dung gồm:
     - Tóm tắt tổng quan.
     - Mục “Điểm chính”.
     - Mục “Khái niệm & entity quan trọng”.
     - Mục “Nguồn” (link lại file trong `raw/` với link title là title của tài liệu).
     - Nếu thêm các media minh họa thì càng tốt
   - Thêm frontmatter với `type: "source"`.

5. **Cập nhật topic/overview (nếu liên quan)**
  - Mở trang topic tương ứng trong `topics/` (tạo mới nếu chưa có) hoặc có thể bổ sung nội dung vào các topic hiện có.
  - Nếu cần tạo topic mới, hãy tạo topic, tồi tạo navigation link trong mkdocs.yml.

6. **Cập nhật/ tạo các trang entity & concept**
   - Với mỗi entity/concept quan trọng:
     - Nếu đã có trang: mở và cập nhật phần nội dung source summary mới được tạo.
     - Nếu chưa có: tạo trang mới trong `entities/` hoặc `concepts/`.
   - Đảm bảo có link qua lại:
     - Từ source summary → các entity/concept.
     - Từ entity/concept → source (mục “Nguồn”).
   - Cập nhật danh mục entity, concept vào file index.md của mỗi mục này. Danh mục này được phân loại theo thứ tự A, B, C

7. **Cập nhật index.md**
   - Thêm dòng mới trong section tương ứng (Sources, Entities, Concepts, Topics…).

8. **Ghi log**
   - Append entry mới vào `wiki/log.md` theo format ở phần 4.

9. **Yêu cầu**
   - Tuyệt đối không sửa, xóa các nội dung cũ trong quy trình này

---

## 6. Workflow: LINT (bảo trì wiki)

Khi người dùng yêu cầu “kiểm tra sức khỏe wiki” hoặc định kỳ được chỉ định:

1. **Quét cấu trúc**
   - Liệt kê các file trong `docs/wiki/`.
   - Đọc `index.md` và so sánh với thực tế:
     - File có trong `docs/wiki/` mà không có trong index → đề xuất thêm.
     - Link chết trong index → cần sửa.

2. **Tìm mâu thuẫn & thông tin cũ**
   - Với các concept/topic quan trọng, đọc các trang liên quan và:
     - Tìm claim mâu thuẫn hoặc bị nguồn mới update.
     - Đánh dấu phần “Cần kiểm tra lại” nếu không chắc.

3. **Phát hiện trang mồ côi & thiếu**
   - “Trang mồ côi”: ít hoặc không có inbound link.
     - Đề xuất thêm link từ nơi khác (gợi ý trong log hoặc nói với người dùng).
   - “Concept/entity chỉ được nhắc tới nhưng chưa có trang riêng”.
     - Tạo skeleton page (stub) với vài dòng mô tả và TODO.

4. **Ghi log lint**
   - Tạo entry mới trong `wiki/log.md` mô tả:
     - Những vấn đề đã phát hiện.
     - Những sửa chữa đã thực hiện.
     - Gợi ý hành động tiếp theo cho người dùng.

---

## 7. Nguyên tắc chung

- **An toàn dữ liệu**: không xoá file trong `docs/wiki/` trừ khi người dùng yêu cầu rõ ràng. Nếu cần, có thể “deprecate” bằng cách ghi chú trong file thay vì xoá.
- **Nhỏ nhưng chắc**: mỗi lượt thao tác nên chạm số file vừa phải (vd 5–15 file) để dễ kiểm soát.
- **Luôn để lại dấu vết**:
  - Cập nhật `updated` trong frontmatter khi sửa trang.
  - Append log cho mọi ingest lớn, query được ghi vào wiki, lint.
- **Nói rõ với người dùng**:
  - Khi có nhiều cách tổ chức, đề xuất vài lựa chọn và hỏi họ.
  - Nếu không chắc ý định, hỏi lại thay vì tự đoán.

## 8. Danh mục các chủ đề (WIKI_TOPIC)
Nội dung của mọi loại tài liệu sẽ được phân chia thành các loại loại khác nhau theo hình cây và không hạn chế số lượng và cấu trúc độ sâu của cây phân loại. Có thể thêm các loại khác nếu những loại hiện tại không phù hợp.
      1. AI Fundamental: Kiến thức nền tảng về AI, LLM models, foundation models.

      2. Building AI applications: Chủ đề này bao gồm các kỹ thuật xây dựng giải pháp AI như: ứng dụng AI,  workflow, thu thập dữ xử lý dữ liệu cho AI model, training, develop, testing, bảo mật và vận hành (AI Ops), xây dựng AI Agent...
        - Data processing: Các công cụ và thư viện để xử lý dữ liệu, trích xuất tài liệu, ETL pipeline.
        - Building Agents: Chủ đề này tập trung vào việc xây dựng các AI Agents, bao gồm kiến trúc, orchestration, và các ứng dụng thực tế.

      3. Agent Applications: Tập hợp các nội dung nói về các ứng dụng Agents và các tools, MCP, và plugins cho các ứng dụng này. Có thể phân loại thành các chủ đề nhỏ:
        - Builder agents: là các tác nhân AI hỗ trợ lập trình viên trong phát triển phần mềm - viết code, debug, refactor, và xử lý documents/security testing.
        - Personal agents: là các tác nhân AI tập trung vào việc hỗ trợ cá nhân trong cuộc sống hàng ngày và xây dựng mối quan hệ lâu dài với người dùng.
        - Research agents: Các tác nhân AI chuyên biệt cho quy trình nghiên cứu khoa học.

---

Khi nhận được yêu cầu từ người dùng (ingest, query, lint), hãy áp dụng các workflow trên, sử dụng các skill của Nanobot (đọc/ghi file, liệt kê, search…) để thao tác trực tiếp trên repo này.

Let start this document project with mkdocs, read the CLAUDE.md and update entire project for me.