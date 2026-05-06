---
title: "Obsidian"
type: "source"
tags: ["obsidian", "notes", "markdown", "knowledge-base", "second-brain", "personal-tool"]
created: "2026-05-05"
updated: "2026-05-05"
sources: ["raw/obsidian_20260505.md"]
category: "Building_AI_applications"
---

# Obsidian

Ứng dụng ghi chú và quản lý "second brain" dựa trên Markdown — xây dựng và tổ chức kho kiến thức cá nhân dưới dạng các file .md liên kết với nhau như một graph kiến thức. Dữ liệu lưu local, offline-first, hỗ trợ plugin phong phú.

**Website**: [obsidian.md](https://obsidian.md/)  
**License**: Proprietary (free for personal use)

## Overview

Obsidian là một ứng dụng ghi chú mạnh mẽ cho việc xây dựng "second brain" — kho kiến thức cá nhân được tổ chức dưới dạng các file Markdown thuần (.md) với hệ thống liên kết hai chiều (backlinks) và Graph View để visualize mối quan hệ giữa các ghi chú.

Điểm khác biệt lớn nhất so với các ứng dụng ghi chú khác là **dữ liệu hoàn toàn thuộc về bạn** — lưu trên ổ đĩa local dưới dạng file .md, không phụ thuộc vào cloud hay định dạng độc quyền.

## Obsidian dùng để làm gì?

- **Ghi chú cá nhân** — nhật ký, journal, daily notes cho công việc và cuộc sống
- **Knowledge base / Second brain** — lưu tài liệu, ý tưởng, trích dẫn, tài liệu nghiên cứu, meeting notes cho dev, researcher, người học
- **Quản lý dự án** — project docs, roadmap, task list nhờ hệ thống liên kết, tìm kiếm và plugin
- **Viết tài liệu kỹ thuật** — blog draft, documentation bằng Markdown, hỗ trợ LaTeX và code blocks

## Các tính năng chính

### 1. Markdown Editor & File .md

- Đầy đủ cú pháp Markdown: heading, list, table, bold/italic, link, image
- **LaTeX** cho công thức toán, **code blocks** với syntax highlighting
- File .md thuần — tương thích với VS Code, Git, static site generator, và các Markdown editor khác

### 2. Vault và Tổ chức Dữ liệu

- Mỗi **vault** là một thư mục trên máy chứa hệ thống folder + file .md
- Hỗ trợ **nhiều vault song song** — tách biệt kiến thức giữa cá nhân, công việc, side project, nghiên cứu
- **Help Vault** — tài liệu hướng dẫn tích hợp sẵn trong app

### 3. Link hai chiều và Graph View

- **Backlinks** — liên kết nội bộ giữa các note, thấy rõ note nào đang trỏ đến note nào
- **Graph View** — hiển thị toàn bộ vault dưới dạng mạng lưới node–edge, zoom, filter, tô màu theo cụm chủ đề

### 4. Tìm kiếm, Tag, Metadata

- Tìm kiếm toàn văn bản cực nhanh, hỗ trợ query nâng cao và filter
- **Tag** và **YAML frontmatter** để thêm metadata (status, topic, project…) cho ghi chú

### 5. Tiện ích Ghi chú Nâng cao

- **Outline** — mục lục theo heading, navigation dễ dàng trong note dài
- **Daily notes** — tạo note theo ngày (YYYY-MM-DD) cho journal, worklog, review
- **Random notes** — mở ngẫu nhiên một note để gợi ý ý tưởng hoặc ôn lại kiến thức

### 6. Plugin và Mở rộng

- **Core plugins** — Calendar, Daily Notes, Outline, Random Note, Backlinks…
- **Community plugins** — Kanban, Dataview, Tasks, Templater, Excalidraw, Calendar, Periodic Notes…
- Customizable: giao diện, theme, hotkey, template cho workflow cá nhân

### 7. Offline, Hiệu năng và Quyền riêng tư

- **100% offline** — không cần internet, tìm kiếm cục bộ nên rất nhanh
- **Dữ liệu local** — file .md trên file system, dễ backup bằng Git
- **Sync options** — Dropbox, iCloud, Git, hoặc Obsidian Sync (trả phí)

## Tại sao Obsidian phù hợp cho Personal Agent workflow?

Obsidian không chỉ là công cụ ghi chú — nó là **nền tảng kiến thức cá nhân** có thể tích hợp với AI agents:

- File .md thuần dễ dàng để AI agents đọc, viết, và liên kết giữa các note
- Graph View và backlinks giúp agents hiểu mối quan hệ giữa các concept trong knowledge base
- Plugin system cho phép mở rộng để tích hợp với LLM APIs, auto-generate notes, hay semantic search
- Local-first đảm bảo privacy cho personal knowledge — dữ liệu không bao giờ rời khỏi máy nếu bạn muốn

## Nguồn

- [Obsidian Raw Source](../../raw/obsidian_20260505.md)
- [Official Website](https://obsidian.md/)

## Liên kết liên quan

- [Personal Agents](../topics/personal_agent.md) - Topic covering personal AI assistants
- [Understand Anything](../sources/understand_anything.md) - Knowledge graph plugin for codebase/wiki analysis
- [Voicebox](../sources/voicebox.md) - Local-first AI voice studio
