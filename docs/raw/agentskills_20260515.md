# Agent Skills — Open Standard for AI Agent Extensibility

**Website**: https://agentskills.io
**GitHub**: https://github.com/agentskills/agentskills
**Org**: Anthropic (original creator), open standard
**Date**: 2026-05-15

---

Agent Skills is a lightweight, open format for extending AI agent capabilities with specialized knowledge and workflows. Originally developed by Anthropic and adopted by a growing ecosystem of agent products.

## What are Agent Skills?

A skill is a folder containing a `SKILL.md` file with metadata (name, description) and instructions that tell an agent how to perform a specific task. Skills can also bundle scripts, reference materials, templates, and other resources.

```
my-skill/
├── SKILL.md          # Required: metadata + instructions
├── scripts/          # Optional: executable code
├── references/       # Optional: documentation
├── assets/           # Optional: templates, resources
└── ...               # Any additional files or directories
```

## Why Agent Skills?

Skills package procedural knowledge and context into portable, version-controlled folders that agents load on demand:

- **Domain expertise**: Capture specialized knowledge as reusable instructions
- **Repeatable workflows**: Turn multi-step tasks into consistent, auditable procedures
- **Cross-product reuse**: Build once, use across any skills-compatible agent

## Progressive Disclosure

Agents load skills in three stages:
1. **Discovery**: Load only name + description at startup (~100 tokens)
2. **Activation**: Load full SKILL.md when task matches (< 5000 tokens recommended)
3. **Execution**: Load scripts/references as needed

## Specification

### SKILL.md Frontmatter
| Field | Required | Description |
|-------|----------|-------------|
| `name` | Yes | 1-64 chars, lowercase + hyphens only |
| `description` | Yes | 1-1024 chars, describes what + when to use |
| `license` | No | License name or file reference |
| `compatibility` | No | Environment requirements |
| `metadata` | No | Arbitrary key-value pairs |
| `allowed-tools` | No | Pre-approved tools (experimental) |

### Optional Directories
- `scripts/` — Executable code (Python, Bash, JavaScript)
- `references/` — Additional documentation loaded on demand
- `assets/` — Templates, images, data files

## Adopted By

Major agents supporting the Agent Skills format include: Claude Code, Claude AI, GitHub Copilot, VS Code, OpenAI Codex, Gemini CLI, Cursor, OpenCode, OpenHands, Goose, JetBrains Junie, Roo Code, Factory, Coder Mux, Amp, Letta, and many more.

## Validation

Use `skills-ref` to validate skills:
```bash
skills-ref validate ./my-skill
```
