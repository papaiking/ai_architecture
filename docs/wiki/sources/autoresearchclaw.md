---
title: "AutoResearchClaw"
type: "source"
category: "Research_agents"
tags: ["research-agent", "academic", "paper-generation", "literature-review", "hitl", "co-pilot"]
created: "2026-04-18"
updated: "2026-05-14"
related_topics: ["topics/Research_agents.md"]
entities: ["aiming_lab.md"]
sources: ["raw/autoresearchclaw.md"]
---

# AutoResearchClaw

- **Source:** [github.com/aiming-lab/AutoResearchClaw](https://github.com/aiming-lab/AutoResearchClaw)
- **Stars:** 12.1k | **License:** MIT | **Tests:** 2,699 passed

Fully autonomous & self-evolving research from idea to paper. Chat an Idea. Get a Paper.

[GitHub](https://github.com/aiming-lab/AutoResearchClaw) | [Discord](https://discord.gg/u4ksqW5P)

## Overview

![AutoResearchClaw Framework v2.0](../media/autoresearchclaw_framework_v2.png)

AutoResearchClaw is a fully autonomous 23-stage research pipeline that turns a single research idea into a conference-ready paper with real literature, hardware-aware experiments, and LaTeX output targeting NeurIPS/ICML/ICLR. v0.4.0 introduces Human-in-the-Loop Co-Pilot mode for guided collaboration.

## Details

- **Org**: aiming-lab
- **Stars**: 12.1k
- **Forks**: 1.4k
- **Commits**: 235
- **License**: MIT
- **Tests**: 2,699 passed
- **Languages**: Python 3.11+

## Latest Updates

- **v0.4.0** (Apr 2026) — Human-in-the-Loop Co-Pilot System with 6 intervention modes, Idea Workshop, Baseline Navigator, Paper Co-Writer, SmartPause, cost guardrails, claim verification, branch exploration
- **v0.3.2** — Cross-Platform Support, ACP-compatible agents (Claude Code, Codex CLI, Copilot CLI, Gemini CLI, Kimi CLI), messaging platforms via OpenClaw bridge, anti-fabrication system
- **v0.3.1** — OpenCode Beast Mode for complex experiments
- **v0.3.0** — MetaClaw Integration for cross-run learning (+18.3% robustness)
- **v0.2.0** — CodeAgent, BenchmarkAgent, FigureAgent subsystems
- **v0.1.0** — Initial release: fully autonomous 23-stage pipeline

## Key Features

- **End-to-End Pipeline** — 23 stages, 8 phases: Scoping → Literature → Synthesis → Design → Execution → Analysis → Writing → Finalization
- **Multi-Source Literature** — Real papers from OpenAlex, Semantic Scholar & arXiv with query expansion and deduplication
- **4-Layer Citation Verification** — arXiv ID → CrossRef/DataCite → title match → LLM relevance scoring
- **Hardware-Aware Execution** — Auto-detects GPU (NVIDIA CUDA / Apple MPS / CPU-only)
- **OpenCode Beast Mode** — Complex experiments auto-routed to OpenCode
- **HITL Co-Pilot (v0.4.0)** — 6 intervention modes with Idea Workshop, Baseline Navigator, Paper Co-Writer, SmartPause
- **Anti-Fabrication** — VerifiedRegistry enforces ground-truth data, auto-diagnoses failed experiments
- **Claim Verification** — Inline fact-checking against collected literature
- **Branch Exploration** — Fork pipeline to explore multiple hypotheses simultaneously
- **Conference-Grade Writing** — NeurIPS/ICML/ICLR LaTeX templates (5,000-6,500 words)
- **MetaClaw Integration** — Cross-run learning from failures (+18.3% robustness)
- **Skills Library** — 19 pre-loaded skills + custom skills support + community skills
- **ACP Support** — Claude Code, Codex CLI, Copilot CLI, Gemini CLI, Kimi CLI as backends

## Intervention Modes (v0.4.0)

| Mode | Command | Description |
|------|---------|-------------|
| **Full Auto** | `--auto-approve` | No human intervention |
| **Gate Only** | `--mode gate-only` | Pause at gate stages (5, 9, 20) |
| **Checkpoint** | `--mode checkpoint` | Pause at phase boundaries (8 checkpoints) |
| **Co-Pilot** | `--mode co-pilot` | Deep collaboration at critical stages |
| **Step-by-Step** | `--mode step-by-step` | Pause after every stage |
| **Express** | `--mode express` | Quick review — 3 most critical gates |
| **Custom** | `--mode custom` | Per-stage policies via `stage_policies` config |

Co-pilot capabilities: Idea Workshop (hypothesis co-creation), Baseline Navigator (experiment design review), Paper Co-Writer (collaborative drafting), SmartPause (confidence-driven pausing), cost guardrails, escalation policies, ALHF intervention learning.

## Pipeline Stages

```
Phase A: Research Scoping      Stage 1-2
Phase B: Literature Discovery  Stage 3-6
Phase C: Knowledge Synthesis    Stage 7-8
Phase D: Experiment Design      Stage 9-11
Phase E: Experiment Execution   Stage 12-13
Phase F: Analysis & Decision    Stage 14-15
Phase G: Paper Writing          Stage 16-19
Phase H: Finalization          Stage 20-23
```

Gate stages (5, 9, 20) pause for approval. Stage 15 can trigger REFINE or PIVOT. Co-pilot collaboration at Stages 7-8, 9, 16-17.

## MetaClaw Integration Results

| Metric | Baseline | With MetaClaw | Improvement |
|--------|----------|---------------|-------------|
| Stage retry rate | 10.5% | 7.9% | -24.8% |
| Refine cycle count | 2.0 | 1.2 | -40.0% |
| Pipeline stage completion | 18/19 | 19/19 | +5.3% |
| Overall robustness | 0.714 | 0.845 | +18.3% |

## OpenClaw & ACP Integration

Runs via OpenClaw ("Research X" → done), or any ACP-compatible agent (Claude Code, Codex CLI, Copilot CLI, Gemini CLI, Kimi CLI, OpenCode). Bridge adapter system with 6 optional capabilities (cron, messaging, memory, sessions spawn, web fetch, browser).

## Skills Library

19 pre-loaded built-in skills (scientific writing, literature search, chemistry, biology, etc.) + community skills. Install custom skills via `researchclaw skills install` or drop a `SKILL.md` into `.claude/skills/`.

## Showcase

8 papers across 8 domains (math, statistics, biology, computing, NLP, RL, vision, robustness) — generated autonomously or with co-pilot guidance.

## Ethics & Responsible Use

Comprehensive ethics guidelines covering academic integrity, transparency, citation verification, misuse prevention, and dual-use considerations. AI-generated papers are drafts requiring human review before any submission.

## Output

- `paper_draft.md` — Full academic paper
- `paper.tex` — Conference-ready LaTeX
- `references.bib` — Real BibTeX references
- `verification_report.json` — Citation integrity verification
- `experiment_runs/` — Generated code + results
- `charts/` — Auto-generated comparison charts
- `reviews.md` — Multi-agent peer review
- `deliverables/` — Compile-ready for Overleaf

## Quick Start

```bash
git clone https://github.com/aiming-lab/AutoResearchClaw.git
cd AutoResearchClaw
pip install -e .
researchclaw setup
researchclaw init
export OPENAI_API_KEY="sk-..."
researchclaw run --topic "Your research idea" --auto-approve
```

## Nguồn

- [Raw Source](../../raw/autoresearchclaw.md)
- [GitHub Repository](https://github.com/aiming-lab/AutoResearchClaw)

## Liên kết liên quan

- [Research Agents](../topics/Research_agents.md)
- [Aiming Lab](../entities/aiming_lab.md)
- [MetaClaw](https://github.com/aiming-lab/MetaClaw) — Cross-run learning
- [OpenClaw](https://github.com/openclaw/openclaw) — Agent platform
