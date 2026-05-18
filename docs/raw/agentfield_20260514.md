# AgentField — The AI Backend

**Org**: Agent-Field
**GitHub**: https://github.com/Agent-Field/agentfield
**License**: Apache 2.0
**Stars**: 1.8k
**Forks**: 290
**Latest Release**: v0.1.84 (May 11, 2026)
**Commits**: 1,029
**Languages**: Go (50.4%), TypeScript (29.4%), Python (19.2%)
**Website**: https://agentfield.ai
**Date**: 2026-05-14

---

AgentField is an open-source control plane that lets you build AI agents callable by any service in your stack — frontends, backends, other agents, cron jobs — just like any other API. You write agent logic in Python, Go, or TypeScript. AgentField turns it into production infrastructure: routing, coordination, memory, async execution, and cryptographic audit trails. Every function becomes a REST endpoint. Every agent gets a cryptographic identity. Every decision is traceable.

## Key Concepts

- **Reasoners & Skills** — `@app.reasoner()` for AI judgment, `@app.skill()` for deterministic code
- **Structured AI** — `app.ai(schema=MyModel)` returns typed Pydantic/Zod output from any LLM
- **Harness** — `app.harness("Fix the bug")` dispatches multi-turn tasks to Claude Code, Codex, Gemini CLI, or OpenCode
- **Cross-Agent Calls** — `app.call("other-agent.func")` routes through the control plane with full tracing
- **Discovery** — `app.discover(tags=["ml*"])` finds agents across the mesh
- **Memory** — `app.memory.set()` / `.get()` / `.search()` — KV + vector search, four scopes

## Production Infrastructure

### Execution Engine
- Sync REST execution, async fire-and-forget, SSE streaming
- No timeout limits — agents run for hours or days
- Auto retries + exponential backoff, durable queue (PostgreSQL)
- Webhooks with HMAC-SHA256 signing

### Human-in-the-Loop
- `app.pause()` suspends execution for human approval
- Crash-safe state, configurable timeouts with auto-escalation

### Canary Deployments
- Traffic weight routing (5% → 50% → 100%), A/B testing, blue-green rollouts
- Per-version health tracking, unhealthy versions auto-removed

### Identity & Governance
- Every agent gets a W3C DID with Ed25519 keys
- Verifiable Credentials — tamper-proof receipt per execution
- Tag-based access policies with cryptographic verification
- Agent notes for audit logging

### Observability
- Automatic workflow DAG visualization
- Prometheus /metrics, structured JSON logging
- Execution timeline and correlation IDs

## Language Support
- Python SDK, Go SDK, TypeScript SDK
- REST API for any language
- MCP server integration via `af add --mcp --url <server>`

## Quick Start
```bash
curl -fsSL https://agentfield.ai/install.sh | bash
# In Claude Code: /agentfield <description>
# Or manual:
af init my-agent --defaults
cd my-agent && pip install -r requirements.txt
af server  # Dashboard at localhost:8080
python main.py  # Agent auto-registers
```

## Examples
- Autonomous Engineering Team — one API call spins up PM, architect, coders, QA
- Deep Research Engine — recursive research with parallel agents (10,000+ per query)
- Reactive MongoDB Intelligence — document enrichment with risk scores
- Autonomous Security Audit — 250 coordinated agents for vulnerability analysis
