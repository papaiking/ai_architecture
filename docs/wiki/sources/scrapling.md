---
title: "Scrapling"
type: "source"
category: "Building_AI_applications"
tags: ["web-scraping", "crawling", "adaptive-parser", "anti-bot"]
created: "2026-04-18"
updated: "2026-04-18"
related_topics: ["topics/Building_AI_apps.md"]
---

# Scrapling

- **Type**: Web Scraping Framework

## Overview

Scrapling is an adaptive Web Scraping framework that handles everything from a single request to a full-scale crawl. Its parser learns from website changes and automatically relocates elements when pages update. The fetchers bypass anti-bot systems like Cloudflare Turnstile out of the box, and its spider framework scales to concurrent, multi-session crawls with pause/resume and automatic proxy rotation.

## Details

- Org: D4Vinci
- Stars: 37.7k
- Forks: 3.3k
- License: BSD-3-Clause
- Commits: 1,400+
- Language: Python 99.9%

## Key Features

- Adaptive element tracking that relocates elements after website changes using intelligent similarity algorithms
- Scrapy-like Spider API with async parse callbacks, concurrent crawling, and per-domain throttling
- Multiple fetcher types: Fetcher (HTTP), StealthyFetcher (anti-bot bypass), DynamicFetcher (browser automation)
- Multi-session support with persistent cookies and state across requests
- Built-in proxy rotation with cyclic or custom strategies
- MCP server for AI-assisted web scraping and data extraction
- CLI with interactive shell and extract command for terminal-based scraping
- Pause & resume with checkpoint-based crawl persistence
- Streaming mode for real-time stats and UI integration
- Full type hints and 92% test coverage

## Usage Example

```python
from scrapling.fetchers import Fetcher, StealthyFetcher
from scrapling.spiders import Spider

# Basic HTTP request
page = Fetcher.get('https://quotes.toscrape.com/')
quotes = page.css('.quote .text::text').getall()

# Stealthy fetching (bypasses Cloudflare)
page = StealthyFetcher.fetch('https://example.com', headless=True, solve_cloudflare=True)
products = page.css('.product', auto_save=True)

# Full spider with concurrent crawling
class QuotesSpider(Spider):
    name = "quotes"
    start_urls = ["https://quotes.toscrape.com/"]
    concurrent_requests = 10

    async def parse(self, response):
        for quote in response.css('.quote'):
            yield {"text": quote.css('.text::text').get()}

result = QuotesSpider().start()
```

## Installation

```bash
pip install scrapling                    # Parser only
pip install "scrapling[fetchers]"     # With fetchers
pip install "scrapling[all]"        # Everything including CLI
scrapling install                   # Download browsers
```

## CLI Usage

```bash
scrapling shell                    # Interactive scraping shell
scrapling extract get 'https://example.com' content.md
scrapling extract stealthy-fetch 'https://example.com' output.html --solve-cloudflare
```

## Performance

- 10x faster JSON serialization than standard library
- 784x faster than BeautifulSoup
- 41x faster than Selectolax

## Related Entities

- [D4Vinci](https://github.com/D4Vinci) - Author
- Playwright - Browser automation used by DynamicFetcher
- Scrapy - Similar Python scraping framework

---

## Source

- [Raw Source](../../raw/scrapling.md)
- [GitHub](https://github.com/simonw/scrapling)

## Related Topics

- [Building AI Applications](../topics/Building_AI_apps.md)