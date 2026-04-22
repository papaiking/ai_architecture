---
title: "Feynman - AI Research Agent"
type: "source"
category: "Research_agents"
tags: ["research", "agent", "papers", "literature", "replication"]
created: "2026-04-21"
updated: "2026-04-21"
sources: ["raw/feynman.md"]
related_topics: ["topics/Research_agents.md"]
---

# Feynman - AI Research Agent

**Organization**: getcompanion-ai  
**Stars**: 5.7k

## Overview

The open source AI research agent. Tự động tìm kiếm papers, web, thực hiện research, tạo literature review, audit papers, và replicate experiments.

## Commands

```
$ feynman "what do we know about scaling laws"
→ Searches papers and web, produces a cited research brief

$ feynman deepresearch "mechanistic interpretability"
→ Multi-agent investigation with parallel researchers, synthesis, verification

$ feynman lit "RLHF alternatives"
→ Literature review with consensus, disagreements, open questions

$ feynman audit 2401.12345
→ Compares paper claims against the public codebase

$ feynman replicate "chain-of-thought improves math"
→ Replicates experiments on local or cloud GPUs
```

## Workflows

| Command | Description |
|---------|------------|
| `/deepresearch` | Multi-agent investigation |
| `/lit` | Literature review from papers |
| `/review` | Simulated peer review |
| `/audit` | Paper vs. codebase mismatch |
| `/replicate` | Run experiments on GPUs |
| `/compare` | Source comparison matrix |
| `/draft` | Paper-style draft |
| `/autoresearch` | Autonomous experiment loop |
| `/watch` | Recurring research watch |

## Agents

- **Researcher** — gather evidence across papers, web, repos, docs
- **Reviewer** — simulated peer review with severity-graded feedback
- **Writer** — structured drafts from research notes
- **Verifier** — inline citations, source URL verification

## Skills & Tools

- **AlphaXiv** — paper search và analysis
- **Docker** — isolated container execution
- **Web search** — Gemini or Perplexity
- **Modal/RunPod** — GPU compute for experiments

---

## Related Topics

- [Research Agents](../topics/Research_agents.md)

---

## Source

- [Raw Source](../../raw/feynman.md)
- [GitHub](https://github.com/getcompanion-ai/feynman)