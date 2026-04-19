# SkillClaw

## Overview

SkillClaw makes LLM agents progressively better by evolving reusable skills from real session data. Let Skills Evolve Collectively with Agentic Evolver.

## Details

- Org: AMAP-ML
- Stars: 741
- Forks: 78
- License: MIT
- Language: Python 98.9%, Shell 1.1%
- Paper: arXiv:2604.08377

## Key Features

- **Collective Skill Evolution** - Skills evolve from every session, across agents, devices, and users
- **Auto-evolve, auto-deduplicate, auto-improve** - Makes learned content actually count
- **Single user + multiple agents** - One unified skill library across all agents
- **Multiple devices** - Skills follow you, not your machine
- **Team sharing** - Join shared groups, experience compounds
- **Hermes integration** - Native integration with Hermes agent
- **Broad compatibility** - Works with Hermes, OpenClaw, QwenPaw, IronClaw, PicoClaw, ZeroClaw, NanoClaw, NemoClaw

## Components

### 1. Client Proxy
Local API proxy that intercepts agent requests, records session artifacts, and manages local skill library.

### 2. Evolve Server (Optional)
Service that reads session data, evolves/creates skills, and writes back. Two engines:
- `workflow`: Fixed 3-stage LLM pipeline (Summarize → Aggregate → Execute)
- `agent`: OpenClaw-driven agent workspace with direct skill editing

## Quick Start

```bash
# Install
git clone https://github.com/AMAP-ML/SkillClaw.git && cd SkillClaw
bash scripts/install_skillclaw.sh
source .venv/bin/activate

# Setup
skillclaw setup

# Start
skillclaw start --daemon
```

## Hermes Integration

```bash
# If using Hermes
skillclaw setup  # choose hermes for CLI agent
skillclaw start --daemon

# Verify
hermes chat -Q -m skillclaw-model -q "Reply with exactly HERMES_SKILLCLAW_OK"
```

## Storage Support

- Local filesystem
- Alibaba OSS
- AWS S3

## Deployment Models

1. **Single user + auto-evolution**: Client proxy + evolve server on same machine
2. **Team / shared group**: Multiple clients + shared storage + one evolve server

## Related Projects

- [MetaClaw](https://github.com/aiming-lab/MetaClaw) - Agentic evolver foundation
- [Hermes](https://github.com/NousResearch/hermes-agent) - Integration target
- [OpenClaw](https://github.com/openclaw/openclaw) - Agent platform

## Citation

```bibtex
@article{ma2026skillclaw,
  title={SkillClaw: Let Skills Evolve Collectively with Agentic Evolver},
  author={Ma, Ziyu and others},
  journal={arXiv preprint arXiv:2604.08377},
  year={2026}
}
```

---

*Source: https://github.com/AMAP-ML/SkillClaw*
*Accessed: 2026-04-20*