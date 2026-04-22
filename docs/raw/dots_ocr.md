---
title: "dots.ocr"
type: "source"
category: "AI_Fundamental"
tags: ["vision", "ocr", "document", "multimodal", "vlm"]
created: "2026-04-21"
updated: "2026-04-21"
sources: ["https://github.com/rednote-hilab/dots.ocr"]
---

# dots.ocr

**Organization**: rednote-hilab
**Stars**: 8.5k
**License**: MIT

## Overview

Multilingual Document Layout Parsing in a Single Vision-Language Model. SOTA performance among models of comparable size in multilingual document parsing.

## Key Features

- **Multilingual OCR**: Recognize virtually any human script
- **Document Parsing**: Parse documents, PDFs, images
- **Structured Graphics**: Convert charts/diagrams to SVG code
- **Web Parsing**: Parse web screens
- **Scene Text Spotting**: Detect and recognize scene text

## Performance

### Document Parsing (Elo Score)

| Model | olmOCR-Bench | OmniDocBench | XDocParse | Average |
|-------|--------------|--------------|-----------|---------|
| dots.mocr | 1104.4 | 1059.0 | 1210.7 | **1124.7** |
| Gemini 3 Pro | 1180.4 | 1128.0 | 1323.7 | 1210.7 |

### Structured Graphics (SVG)

| Model | Unisvg | Chartmimic | Design2Code | Score |
|-------|--------|------------|------------|-------|
| dots.mocr-svg | **0.860** | **0.931** | **0.902** | **0.901** |

## Usage

```bash
# Installation
conda create -n dots_mocr python=3.12
git clone https://github.com/rednote-hilab/dots.mocr.git
cd dots.mocr
pip install -e .

# vLLM inference
CUDA_VISIBLE_DEVICES=0 vllm serve rednote-hilab/dots.mocr --tensor-parallel-size 1

# Parse document
python3 dots_mocr/parser.py demo/demo_image1.jpg
python3 dots_mocr/parser.py demo/demo_pdf1.pdf
```

## Models

- **dots.mocr**: General document parsing
- **dots.mocr-svg**: Specialized for SVG code generation
- **dots.ocr.base**: Foundation VLM for OCR tasks

---

## Source

- [Wiki Source](../wiki/sources/dots_ocr.md)
- [GitHub](https://github.com/rednote-hilab/dots.ocr)