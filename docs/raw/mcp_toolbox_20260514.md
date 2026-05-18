# MCP Toolbox for Databases

- **Source:** https://github.com/googleapis/mcp-toolbox
- **Author:** Google (googleapis)
- **Stars:** 15.2k
- **License:** Apache-2.0
- **Language:** Go
- **Fetched:** May 14, 2026

---

MCP Toolbox for Databases is an open source MCP server that connects AI agents, IDEs, and applications directly to enterprise databases.

Dual purpose:
1. **Ready-to-use MCP Server (Build-Time):** Instant database access from Gemini CLI, Google Antigravity, Claude Code, Codex via prebuilt generic tools (list_tables, execute_sql, etc.)
2. **Custom Tools Framework (Run-Time):** Framework to build specialized, secure AI tools with structured queries, semantic search, and NL2SQL

Originally named "Gen AI Toolbox for Databases", renamed to align with MCP.

## Supported Databases

- **Google Cloud:** AlloyDB, BigQuery, Cloud SQL (PostgreSQL, MySQL, SQL Server), Spanner, Firestore, Knowledge Catalog
- **Others:** PostgreSQL, MySQL, SQL Server, Oracle, MongoDB, Redis, Elasticsearch, CockroachDB, ClickHouse, Couchbase, Neo4j, Snowflake, Trino

## Key Features

- Prebuilt generic tools for instant data exploration
- Custom tools framework via tools.yaml (sources, tools, toolsets, prompts)
- Connection pooling, integrated auth (IAM), OpenTelemetry
- SDKs: Python, JS/TS, Go, Java
- Framework integrations: LangChain, LlamaIndex, Genkit, ADK
- Agent Skills generation (agentskills.io spec)
- Toolbox UI for testing (--ui flag)
- Dynamic config reloading

## Installation

```sh
# Binary
curl -L -o toolbox https://storage.googleapis.com/mcp-toolbox-for-databases/v1.2.0/darwin/arm64/toolbox

# Docker
docker pull us-central1-docker.pkg.dev/database-toolbox/toolbox/toolbox:1.2.0

# Homebrew
brew install mcp-toolbox

# NPM
npx @toolbox-sdk/server --config tools.yaml
```
