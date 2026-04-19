# AutoResearchClaw

## Overview

Fully autonomous research pipeline that turns a single research idea into a conference-ready paper. 23-stage pipeline covering literature review, hypothesis generation, experiments, and paper writing. Targets NeurIPS/ICML/ICLR.

## Details

- **Org**: aiming-lab
- **Stars**: N/A (check GitHub)
- **License**: MIT

## Key Features

- **End-to-End Pipeline** — 23 stages, 8 phases: Scoping → Literature → Synthesis → Design → Execution → Analysis → Writing → Finalization
- **Multi-Source Literature** — Real papers from OpenAlex, Semantic Scholar & arXiv
- **4-Layer Citation Verification** — arXiv ID → CrossRef/DataCite → title match → LLM relevance scoring
- **Hardware-Aware Execution** — Auto-detects GPU (NVIDIA CUDA / Apple MPS / CPU-only)
- **OpenCode Beast Mode** — Complex experiments auto-routed to OpenCode
- **Sandbox Experiments** — AST-validated code, self-healing, iterative refinement
- **Co-Pilot Mode** — Human-in-the-loop collaboration at critical stages
- **Conference-Grade Writing** — NeurIPS/ICML/ICLR LaTeX templates
- **MetaClaw Integration** — Cross-run learning from failures

## Intervention Modes

| Mode | Description |
|------|-----------|
| **Full Auto** | No human intervention |
| **Gate Only** | Pause at gate stages (5, 9, 20) |
| **Checkpoint** | Pause at phase boundaries |
| **Co-Pilot** | Deep collaboration at critical stages |
| **Step-by-Step** | Pause after every stage |

## Output

- `paper_draft.md` — Full academic paper
- `paper.tex` — Conference-ready LaTeX
- `references.bib` — Real BibTeX references
- `verification_report.json` — Citation integrity verification
- `experiment_runs/` — Generated code + results
- `charts/` — Auto-generated comparison charts

## Quick Start

```bash
pip install -e . && researchclaw setup && researchclaw init
researchclaw run --topic "Your research idea" --auto-approve
```

## Pipeline Stages

```
Phase A: Research Scoping      (1-2)
Phase B: Literature Discovery  (3-6)
Phase C: Knowledge Synthesis  (7-8)
Phase D: Experiment Design   (9-11)
Phase E: Experiment Execution (12-13)
Phase F: Analysis & Decision (14-15)
Phase G: Paper Writing    (16-19)
Phase H: Finalization    (20-23)
```

---

*Accessed: 2026-04-18*