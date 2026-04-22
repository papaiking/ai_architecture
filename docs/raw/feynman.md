---
title: "Feynman - AI Research Agent"
type: "source"
category: "Research_agents"
tags: ["research", "agent", "papers", "literature", "replication"]
created: "2026-04-21"
updated: "2026-04-21"
sources: ["https://github.com/getcompanion-ai/feynman"]
---

# Feynman - AI Research Agent

**Organization**: getcompanion-ai
**Stars**: 5.7k
**License**: MIT

## Overview

The open source AI research agent. Tự động tìm kiếm papers, web, thực hiện research, tạo literature review, audit papers, và replicate experiments.

## Installation

```bash
# macOS / Linux
curl -fsSL https://feynman.is/install | bash

# Windows (PowerShell)
irm https://feynman.is/install.ps1 | iex
```

## Workflows

| Command | What it does |
|---------|--------------|
| `/deepresearch <topic>` | Multi-agent investigation with parallel researchers |
| `/lit <topic>` | Literature review with consensus, disagreements |
| `/review <artifact>` | Simulated peer review with severity |
| `/audit <item>` | Paper vs. codebase mismatch audit |
| `/replicate <paper>` | Replicate experiments on local/cloud GPUs |
| `/compare <topic>` | Source comparison matrix |
| `/draft <topic>` | Paper-style draft from findings |
| `/autoresearch <idea>` | Autonomous experiment loop |
| `/watch <topic>` | Recurring research watch |

## Agents

- **Researcher** — gather evidence across papers, web, repos, docs
- **Reviewer** — simulated peer review with severity-graded feedback
- **Writer** — structured drafts from research notes
- **Verifier** — inline citations, source URL verification

## Skills & Tools

- **AlphaXiv** — paper search, Q&A, code reading
- **Docker** — isolated container execution
- **Web search** — Gemini or Perplexity
- **Session search** — indexed recall across prior research
- **Preview** — browser and PDF export
- **Modal** — serverless GPU compute
- **RunPod** — persistent GPU pods with SSH

## How it works

Built on Pi for agent runtime, alphaXiv for paper search and analysis. Every output is source-grounded — claims link to papers, docs, or repos with direct URLs.

---

## Source

- [Wiki Source](../wiki/sources/feynman.md)
- [GitHub](https://github.com/getcompanion-ai/feynman)