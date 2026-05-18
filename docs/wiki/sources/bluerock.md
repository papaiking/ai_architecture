---
title: "BlueRock"
type: "source"
tags: ["security", "mcp", "monitoring", "python", "runtime", "opens-source"]
created: "2026-05-05"
updated: "2026-05-05"
sources: ["raw/bluerock_20260505.md"]
category: "Building_Agent_apps"
---

# BlueRock

Lightweight runtime security sensor for Python MCP servers. Monitor MCP tool calls, resource access, session lifecycle, and module imports with zero code changes.

- **GitHub**: [bluerock-io/bluerock](https://github.com/bluerock-io/bluerock)  
- **PyPI**: [bluerock](https://pypi.org/project/bluerock/)  
- **Website**: [bluerock.io](https://www.bluerock.io/)  
- **License**: Apache 2.0

## Overview

BlueRock wraps your Python process and emits structured NDJSON events for security-sensitive operations. It hooks into Python at startup, before your code runs, so nothing slips through. Your code, your dependencies, and their transitive dependencies are all in scope.

Built for **security teams, AppSec engineers, and AI developers** deploying MCP agents. Know exactly what your tools call, which modules load, and what data crosses the wire, without changing a line of code.

## Key Features

- **Zero code changes** — Wrap any script with `python -m bluepython --oss your_script.py`
- **Two-layer hooking** — `wrapt` for MCP protocol, `sys.meta_path` for import monitoring
- **Full MCP coverage** — Tool calls, resource access, sessions, transport connections (stdio, HTTP, SSE)
- **Supply chain visibility** — Every import with SHA-256 hash, version, file path
- **Hooks before your code runs** — Covers your code + all dependencies
- **Open source** — Apache 2.0, inspect and contribute

## What It Monitors

| Category | Events | What It Catches |
|---|---|---|
| **MCP** | `python_mcp_server_init`, `python_mcp_server_add`, `python_mcp_event`, `python_mcp_session_created`, `python_mcp_session_terminated`, `python_mcp_client_connect` | Tool calls, resource access, prompt requests, session lifecycle, transport connections |
| **Imports** | `python_import` | Every module import with name, path, version, SHA-256 |

## Quick Start

### Install from PyPI

```bash
pip install bluerock[oss]

mkdir -p ~/.bluerock
echo '{"enable": true, "mcp": true, "imports": true}' > ~/.bluerock/bluerock-oss.json
python -m bluepython --oss --cfg-dir ~/.bluerock your_script.py
cat ~/.bluerock/event-spool/python-*.ndjson | jq .event
```

### Try MCP Example

```bash
cd examples/mcp/
python -m bluepython --oss mcp_client.py --transport stdio

# See what happened
cat ~/.bluerock/event-spool/python-*.ndjson | jq '.event.meta.name' | sort | uniq -c
```

### Import Monitoring

```bash
echo '{"enable": true, "mcp": true, "imports": true}' > ~/.bluerock/bluerock-oss.json

pip install requests
python -m bluepython --oss examples/core-hooks/import-monitoring/import_monitoring.py

# See every module loaded, with SHA-256 hashes
cat ~/.bluerock/event-spool/python-*.ndjson | jq -r '.event | select(.meta.name == "python_import") | "\(.fullname) \(.version // "n/a") \(.sha256[0:16])..."'
```

## Comparison

| | BlueRock | Manual logging | OpenTelemetry |
|---|---|---|---|
| Code changes | None | Instrument every call | Add spans/traces |
| Covers dependencies | Yes (transitive) | Only what you wrap | Only what you wrap |
| AI/MCP monitoring | Built-in (6 event types) | DIY | No |
| Import verification | SHA256 per module | No | No |
| Output format | NDJSON (structured) | Ad-hoc | OTLP |

## Dashboard (Grafana + Loki)

```bash
cd observe/deploy
./deploy.sh dir ~/.bluerock/event-spool

# Open http://localhost:3000 (login: admin/admin)
```

## Event Format

Every line in the NDJSON log is a timestamped envelope:

```json
{
  "ts": "2026-04-02T10:00:00Z",
  "event": {
    "meta": {
      "name": "python_mcp_server_init",
      "origin": "bluepython",
      "sensor_id": 1,
      "type": "event"
    },
    "server": {
      "name": "test-mcp-server",
      "version": "0.0.1"
    }
  }
}
```

## Supported Platforms

| OS | Architecture | Python |
|---|---|---|
| Linux | x86_64, aarch64 | >= 3.10 |
| macOS | arm64 (Apple Silicon), x86_64 | >= 3.10 |

## Why BlueRock?

Most runtime instrumentation focuses on observability (tracing, metrics). BlueRock focuses on **security**: the operations that matter from a threat-detection perspective.

- **Zero code changes** — No imports, no SDK integration
- **Full dependency coverage** — Your code + all transitive dependencies
- **MCP-native** — Built for the Model Context Protocol ecosystem
- **Supply chain security** — SHA-256 verification on every import

## License

Apache 2.0 — inspect the hooks, contribute new ones, integrate with your own tooling.

## Nguồn

- [BlueRock Raw Source](../../raw/bluerock_20260505.md)
- [GitHub Repository](https://github.com/bluerock-io/bluerock)

## Liên kết liên quan

- [Building Agent Apps](../topics/building_agent_apps.md) - Topic covering agent application development
- [AI Agents](../topics/ai_agents.md) - Overview of AI agents
- [MCP](https://www.anthropic.com/mcp) - Model Context Protocol
