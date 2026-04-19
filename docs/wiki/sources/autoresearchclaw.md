---
title: "AutoResearchClaw"
type: "source"
category: "Research_agents"
tags: ["research-agent", "academic", "paper-generation", "literature-review"]
created: "2026-04-18"
updated: "2026-04-19"
related_topics: ["topics/Research_agents.md"]
entities: ["aiming_lab.md"]
---

# AutoResearchClaw

**Type**: Research Agent

Fully autonomous & self-evolving research from idea to paper. Chat an Idea. Get a Paper.

[GitHub](https://github.com/aiming-lab/AutoResearchClaw) | [Discord](https://discord.gg/u4ksqW5P)

## Overview

AutoResearchClaw is a fully autonomous 23-stage research pipeline that turns a single research idea into a conference-ready paper with real literature, hardware-aware experiments, and LaTeX output targeting NeurIPS/ICML/ICLR.

## Details

- **Org**: aiming-lab
- **Stars**: 11.3k
- **Forks**: 1.3k
- **Commits**: 225
- **License**: MIT
- **Tests**: 2,699 passed
- **Languages**: Python 3.11+

## Latest Updates

- **v0.4.0** (Apr 2026) — Human-in-the-Loop Co-Pilot System with 6 intervention modes, Idea Workshop, Baseline Navigator, Paper Co-Writer, SmartPause, cost guardrails
- **v0.3.2** — Cross-Platform Support, ACP-compatible agents (Claude Code, Codex CLI, Copilot CLI, Gemini CLI, Kimi CLI), messaging platforms via OpenClaw
- **v0.3.1** — OpenCode Beast Mode for complex experiments
- **v0.3.0** — MetaClaw Integration for cross-run learning

## Key Features

- **End-to-End Pipeline** — 23 stages, 8 phases: Scoping → Literature → Synthesis → Design → Execution → Analysis → Writing → Finalization
- **Multi-Source Literature** — Real papers from OpenAlex, Semantic Scholar & arXiv
- **4-Layer Citation Verification** — arXiv ID → CrossRef/DataCite → title match → LLM relevance scoring
- **Hardware-Aware Execution** — Auto-detects GPU (NVIDIA CUDA / Apple MPS / CPU-only)
- **OpenCode Beast Mode** — Complex experiments auto-routed to OpenCode
- **Sandbox Experiments** — AST-validated code, self-healing, iterative refinement (up to 10 rounds)
- **Co-Pilot Mode** — Human-in-the-loop collaboration at critical stages
- **Conference-Grade Writing** — NeurIPS/ICML/ICLR LaTeX templates (5,000-6,500 words)
- **MetaClaw Integration** — Cross-run learning from failures (+18.3% robustness)
- **Skills Library** — 19 pre-loaded skills + custom skills support

## Intervention Modes

| Mode | Command | Description |
|------|---------|-------------|
| **Full Auto** | `--auto-approve` | No human intervention |
| **Gate Only** | `--mode gate-only` | Pause at gate stages (5, 9, 20) |
| **Checkpoint** | `--mode checkpoint` | Pause at phase boundaries (8 checkpoints) |
| **Co-Pilot** | `--mode co-pilot` | Deep collaboration at critical stages |
| **Step-by-Step** | `--mode step-by-step` | Pause after every stage |
| **Express** | `--mode express` | Quick review — 3 most critical gates |

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
# Clone & install
git clone https://github.com/aiming-lab/AutoResearchClaw.git
cd AutoResearchClaw
pip install -e .

# Setup
researchclaw setup
researchclaw init

# Run
export OPENAI_API_KEY="sk-..."
researchclaw run --topic "Your research idea" --auto-approve
```

## OpenClaw Integration

AutoResearchClaw is OpenClaw-compatible. Share the repo URL with OpenClaw and say "Research [topic]" — OpenClaw handles installation and execution automatically.

## Related Projects

- [OpenClaw](https://github.com/openclaw/openclaw) — Agent platform
- [MetaClaw](https://github.com/aiming-lab/MetaClaw) — Cross-run learning

---

## Nguồn

- [GitHub Repository](https://github.com/aiming-lab/AutoResearchClaw)

## Liên kết liên quan

- [Research Agents](../topics/Research_agents.md)
- [Aiming Lab](../entities/aiming_lab.md)