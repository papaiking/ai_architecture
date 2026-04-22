---
title: "Onyx - Open Source AI Platform"
type: "source"
category: "AI_applications"
tags: ["llm", "rag", "enterprise", "search", "chatbot", "mcp", "connectors"]
created: "2026-04-22"
updated: "2026-04-22"
sources: ["raw/onyx.md"]
related_topics: ["topics/ai_applications.md", "topics/agent_applications.md"]
---

# Onyx - Open Source AI Platform

**Organization**: onyx-dot-app
**Stars**: 27.4k
**License**: MIT

## Overview

Onyx (formerly Danswer) is the application layer for LLMs - bringing a feature-rich interface that can be easily hosted by anyone. Onyx enables LLMs through advanced capabilities like RAG, web search, code execution, file creation, deep research and more.

## Key Features

- **Agentic RAG**: Hybrid index + AI Agents for information retrieval
- **Deep Research**: Multi-step research flow. Top of leaderboard as of Feb 2026.
- **Custom Agents**: Build AI Agents with unique instructions, knowledge, and actions
- **Web Search**: Supports Serper, Google PSE, Brave, SearXNG, Firecrawl/Exa
- **Artifacts**: Generate documents, graphics, and downloadable artifacts
- **Actions & MCP**: Interact with external applications with flexible Auth
- **Code Execution**: Execute code in sandbox for data analysis, graphs, file modification
- **Voice Mode**: Text-to-speech and speech-to-text
- **Image Generation**: Generate images from prompts

## Supported LLM Providers

| Type | Examples |
|------|---------|
| Cloud | Anthropic, OpenAI, Gemini |
| Self-hosted | Ollama, LiteLLM, vLLM |

## Deployment Modes

### Onyx Lite
- Lightweight Chat UI
- Under 1GB memory
- Great for testing or Chat UI only

### Standard
- Vector + Keyword index for RAG
- Background containers for job queues
- AI model inference servers
- Performance optimizations (Redis, MinIO)

## Enterprise Features

- **SSO**: Google OAuth, OIDC, SAML + SCIM
- **RBAC**: Role-based access control
- **Analytics**: Usage graphs by teams, LLMs, agents
- **Query History**: Audit usage
- **Whitelabeling**: Custom branding

## Connectors (40+)

Google Drive, Confluence, Slack, Gmail, Salesforce, SharePoint, GitHub, Jira...

## Quick Start

```bash
curl -fsSL https://onyx.app/install_onyx.sh | bash
```

---

## Related Topics

- [AI Applications](../topics/ai_applications.md)
- [Agent Applications](../topics/agent_applications.md)

---

## Source

- [Raw Source](../../raw/onyx.md)
- [GitHub](https://github.com/onyx-dot-app/onyx)
- [Website](https://www.onyx.app)
- [Docs](https://docs.onyx.app)