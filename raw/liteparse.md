# LiteParse

## Overview

Standalone open-source PDF parsing tool focused on fast and light parsing. Provides high-quality spatial text parsing with bounding boxes, without proprietary LLM features or cloud dependencies. Everything runs locally.

## Details

- **Org**: run-llama
- **Stars**: N/A (check GitHub)
- **License**: Apache 2.0

## Key Features

- **Fast Text Parsing** — Spatial text parsing using PDF.js
- **Flexible OCR System** — Built-in Tesseract.js (zero setup), or plug in HTTP OCR servers (EasyOCR, PaddleOCR)
- **Screenshot Generation** — Generate high-quality page screenshots for LLM agents
- **Multiple Output Formats** — JSON and Text
- **Bounding Boxes** — Precise text positioning information
- **Standalone Binary** — No cloud dependencies, runs entirely locally
- **Multi-platform** — Linux, macOS (Intel/ARM), Windows
- **Multi-format Input** — Auto-converts Word, Excel, PPT, images to PDF via LibreOffice/ImageMagick

## Installation

```bash
# Global install via npm
npm i -g @llamaindex/liteparse

# Or via Homebrew (macOS/Linux)
brew tap run-llama/liteparse
brew install llamaindex-liteparse
```

## Usage

```bash
# Basic parsing
lit parse document.pdf

# Parse with JSON output
lit parse document.pdf --format json -o output.json

# Generate screenshots
lit screenshot document.pdf -o ./screenshots

# Batch parsing
lit batch-parse ./input-directory ./output-directory
```

## Library Usage

```typescript
import { LiteParse } from '@llamaindex/liteparse';

const parser = new LiteParse({ ocrEnabled: true });
const result = await parser.parse('document.pdf');
console.log(result.text);
```

## OCR Options

- **Default**: Tesseract.js (zero setup, works out of the box)
- **Optional**: HTTP OCR servers via simple API specification
- **Supported**: EasyOCR, PaddleOCR, or custom HTTP OCR services

---

*Accessed: 2026-04-18*