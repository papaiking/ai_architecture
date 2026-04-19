# OpenDataLoader PDF

## Overview

Open-source PDF parser for AI-ready data extraction and PDF accessibility automation. Ranks #1 in benchmarks (0.907 overall extraction accuracy). Provides Markdown, JSON (with bounding boxes), HTML output. Supports deterministic local mode + AI hybrid mode for complex pages.

## Details

- **Org**: opendataloader-project
- **Stars**: ~17.7k
- **License**: Apache 2.0

## Key Features

- **PDF Data Extraction** — Extract text, tables, images, formulas with correct reading order
- **Bounding Boxes** — Precise element coordinates for source citations in RAG
- **Hybrid Mode** — Routes complex pages to AI backend for +90% table accuracy
- **OCR** — Built-in OCR (80+ languages) for scanned PDFs
- **PDF Accessibility** — Auto-tagging to Tagged PDF (Q2 2026, free under Apache 2.0)
- **AI Safety Filters** — Blocks prompt injection attacks in PDFs
- **Tagged PDF Support** — Preserves native PDF structure tags
- **Multi-language SDKs** — Python, Node.js, Java

## Benchmark Results

| Engine | Overall | Table | Speed (s/page) |
|--------|---------|-------|--------------|
| **opendataloader [hybrid]** | **0.907** | **0.928** | 0.463 |
| docling | 0.882 | 0.887 | 0.762 |
| marker | 0.861 | 0.808 | 53.932 |

## Installation

```bash
pip install -U opendataloader-pdf
```

```python
import opendataloader_pdf

opendataloader_pdf.convert(
    input_path=["file1.pdf", "file2.pdf"],
    output_dir="output/",
    format="markdown,json"
)
```

## Accessibility Pipeline

| Step | Feature | Status |
|------|--------|-------|
| 1. Audit | Read existing PDF tags | ✅ Free |
| 2. Auto-tag → Tagged PDF | Generate structure tags | Q2 2026 (Free) |
| 3. Export PDF/UA | PDF/UA-1/2 compliance | Enterprise |

---

*Accessed: 2026-04-18*