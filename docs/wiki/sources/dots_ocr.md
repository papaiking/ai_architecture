---
title: "dots.ocr"
type: "source"
category: "AI_Fundamental"
tags: ["vision", "ocr", "document", "multimodal", "vlm"]
created: "2026-04-21"
updated: "2026-04-21"
sources: ["raw/dots_ocr.md"]
related_topics: ["topics/foundation_models.md"]
---

# dots.ocr

**Organization**: rednote-hilab  
**Stars**: 8.5k

## Overview

Multilingual Document Layout Parsing in a Single Vision-Language Model. SOTA performance in multilingual document parsing.

## Key Features

- **Multilingual OCR**: Recognize any human script
- **Document Parsing**: PDF, images, documents
- **SVG Generation**: Convert charts/diagrams to SVG code
- **Web Parsing**: Parse web screens
- **Scene Text**: Spot text in natural scenes

## Performance

| Model | olmOCR-Bench | OmniDocBench | XDocParse | Average |
|-------|--------------|--------------|-----------|---------|
| dots.mocr | 1104.4 | 1059.0 | 1210.7 | **1124.7** |

## Usage

```bash
# Parse document
python3 dots_mocr/parser.py demo/demo_image1.jpg
python3 dots_mocr/parser.py demo/demo_pdf1.pdf
```

---

## Related Topics

- [Foundation Models](../topics/foundation_models.md)

---

## Source

- [Raw Source](../../raw/dots_ocr.md)
- [GitHub](https://github.com/rednote-hilab/dots.ocr)