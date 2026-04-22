# Onyx - The Open Source AI Platform

**Organization**: onyx-dot-app
**Stars**: 27.4k
**License**: MIT

## Overview

Onyx (formerly Danswer) is the application layer for LLMs - bringing a feature-rich interface that can be easily hosted by anyone. Onyx enables LLMs through advanced capabilities like RAG, web search, code execution, file creation, deep research and more.

> Deploy with a single command:
> ```
> curl -fsSL https://onyx.app/install_onyx.sh | bash
> ```

## Features

- **Agentic RAG**: Get best in class search and answer quality based on hybrid index + AI Agents for information retrieval
- **Deep Research**: Get in depth reports with a multi-step research flow. Top of leaderboard as of Feb 2026.
- **Custom Agents**: Build AI Agents with unique instructions, knowledge, and actions.
- **Web Search**: Browse the web to get up to date information. Supports Serper, Google PSE, Brave, SearXNG, and others. Comes with an in house web crawler and support for Firecrawl/Exa.
- **Artifacts**: Generate documents, graphics, and other downloadable artifacts.
- **Actions & MCP**: Let Onyx agents interact with external applications, comes with flexible Auth options.
- **Code Execution**: Execute code in a sandbox to analyze data, render graphs, or modify files.
- **Voice Mode**: Chat with Onyx via text-to-speech and speech-to-text.
- **Image Generation**: Generate images based on user prompts.

## Supported LLM Providers

Onyx supports all major LLM providers:

- **Cloud**: Anthropic, OpenAI, Gemini
- **Self-hosted**: Ollama, LiteLLM, vLLM

## Deployment Modes

### Onyx Lite
The Lite mode can be thought of as a lightweight Chat UI. It requires less resources (under 1GB memory) and runs a less complex stack.
It is great for users who want to test out Onyx quickly or for teams who are only interested in the Chat UI and Agents functionalities.

### Standard Onyx
The complete feature set recommended for serious users and larger teams. Additional components:

- Vector + Keyword index for RAG.
- Background containers to run job queues and workers for syncing knowledge from connectors.
- AI model inference servers to run deep learning models used during indexing and inference.
- Performance optimizations for large scale use via in memory cache (Redis) and blob store (MinIO).

## Enterprise Features

- **Collaboration**: Share chats and agents with other members of your organization.
- **Single Sign On**: SSO via Google OAuth, OIDC, or SAML. Group syncing and user provisioning via SCIM.
- **Role Based Access Control**: RBAC for sensitive resources like access to agents, actions, etc.
- **Analytics**: Usage graphs broken down by teams, LLMs, or agents.
- **Query History**: Audit usage to ensure safe adoption of AI in your organization.
- **Custom code**: Run custom code to remove PII, reject sensitive queries, or to run custom analysis.
- **Whitelabeling**: Customize the look and feel of Onyx with custom naming, icons, banners, and more.

## Connectors

Keep knowledge and access up to sync across 40+ connectors:

- Google Drive
- Confluence
- Slack
- Gmail
- Salesforce
- Microsoft Sharepoint
- GitHub
- Jira
- And more...

## Licensing

There are two editions of Onyx:

- **Onyx Community Edition (CE)** is available freely under the MIT license and covers all of the core features for Chat, RAG, Agents, and Actions.
- **Onyx Enterprise Edition (EE)** includes extra features that are primarily useful for larger organizations.

---

**Source**: [GitHub](https://github.com/onyx-dot-app/onyx)
**Date**: 2026-04-22