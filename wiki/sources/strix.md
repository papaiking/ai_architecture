---
title: "Strix"
type: "source"
category: "Builder_agents"
tags: ["security", "vulnerability-scanning", "pentest", "builder-agent"]
created: "2026-04-18"
updated: "2026-04-18"
related_topics: ["topics/builder_agents.md"]
---

# Strix

**Type**: Security Testing Tool

## Overview

Strix is an open-source AI hacker that finds and fixes application vulnerabilities. It acts like a real hacker - running code dynamically, finding vulnerabilities, and validating them through actual proof-of-concepts. Built for developers and security teams who need fast, accurate security testing without false positives from static analysis tools.

## Details

- Org: usestrix
- Stars: 24.2k
- Forks: 2.7k
- License: Apache-2.0
- Commits: 350+

## Key Features

- Full hacker toolkit: HTTP proxy, browser automation, terminal, Python runtime
- Teams of autonomous agents that collaborate and scale
- Real vulnerability validation with proof-of-concepts (not false positives)
- Comprehensive vulnerability detection: IDOR, SQL injection, XSS, SSRF, auth bypass, business logic flaws
- CLI with actionable reports and auto-fix capabilities
- CI/CD integration for GitHub Actions
- Multiple scan modes: black-box, grey-box, white-box
- Diff-scope for pull request security scanning
- Headless mode for automated pipelines

## Usage Example

```bash
# Install
curl -sSL https://strix.ai/install | bash

# Configure AI provider
export STRIX_LLM="openai/gpt-5.4"
export LLM_API_KEY="your-api-key"

# Basic security scan
strix --target ./app-directory

# Black-box web app assessment
strix --target https://your-app.com

# Grey-box authenticated testing
strix --target https://your-app.com --instruction "Test with credentials: user:pass"

# PR diff-scope scan
strix -n --target ./ --scan-mode quick --scope-mode diff --diff-base origin/main

# Focus on specific vulnerabilities
strix --target api.your-app.com --instruction "Focus on IDOR and business logic flaws"
```

## Supported Models

- OpenAI GPT-5.4
- Anthropic Claude Sonnet 4.6
- Google Gemini 3 Pro Preview
- Any OpenRouter model (200+ models)
- Local models via Ollama/LMStudio

## CI/CD Integration

```yaml
name: strix-penetration-test
on: pull_request
jobs:
  security-scan:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v6
        with:
          fetch-depth: 0
      - name: Install Strix
        run: curl -sSL https://strix.ai/install | bash
      - name: Run Strix
        env:
          STRIX_LLM: ${{ secrets.STRIX_LLM }}
          LLM_API_KEY: ${{ secrets.LLM_API_KEY }}
        run: strix -n -t ./ --scan-mode quick
```

## Vulnerability Coverage

- Access Control (IDOR, privilege escalation)
- Injection (SQL, NoSQL, command)
- Server-Side (SSRF, XXE)
- Client-Side (XSS, prototype pollution)
- Business Logic (race conditions)
- Authentication (JWT, session)

## Enterprise Features

- SSO (SAML/OIDC)
- Custom compliance reports
- Custom deployment (VPC/self-hosted)
- BYOK model support
- Dedicated support & SLA

## Related Entities

- [LiteLLM](https://github.com/BerriAI/litellm) - LLM proxy used
- [Caido](https://github.com/caido/caido) - Web security tool
- [Nuclei](https://github.com/projectdiscovery/nuclei) - Vulnerability scanner
- [Playwright](https://github.com/microsoft/playwright) - Browser automation

---

## Nguồn

- raw/strix.md

## Liên kết liên quan

- [Builder Agents](../topics/builder_agents.md)
- [Strix AI](../entities/strix_ai.md)