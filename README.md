# Awesome MCP Servers

> A curated, opinionated collection of production-ready MCP (Model Context Protocol) servers with plug-and-play configurations and tooling.

[![GitHub stars](https://img.shields.io/github/stars/FreeAutomation-Tech/awesome-mcp-servers?style=social)](https://github.com/FreeAutomation-Tech/awesome-mcp-servers/stargazers)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)
[![MCP Spec](https://img.shields.io/badge/MCP-2025--03--26-blue)](https://spec.modelcontextprotocol.io/)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg)](https://github.com/FreeAutomation-Tech/awesome-mcp-servers/pulls)

---

## What is MCP?

The Model Context Protocol (MCP) is an open standard from Anthropic that lets AI agents securely connect to external tools, data sources, and services. Think of it as "USB-C for AI" — one universal interface for all tool integrations.

## Quick Start

```bash
# 1. Test a server instantly
npx -y @modelcontextprotocol/server-filesystem /tmp

# 2. Check if servers are available
python tools/mcp-health-check.py

# 3. Generate your config
python tools/mcp-config-generator.py filesystem github brave-search
```

## Server Collection

### Official (by Anthropic/modelcontextprotocol)

| Server | Description | Tools | Config |
|--------|-------------|-------|--------|
| [Filesystem](servers/official/filesystem.md) | File read/write/search with scoped access | `read_file`, `write_file`, `search_files` | `npx -y @modelcontextprotocol/server-filesystem /path` |
| [GitHub](servers/official/github.md) | Full GitHub API — repos, issues, PRs, code search | `search_repos`, `create_issue`, `search_code` | `npx -y @modelcontextprotocol/server-github` + `GITHUB_TOKEN` |
| [Slack](servers/official/slack.md) | Messaging, search, channel management | `post_message`, `search_messages` | `npx -y @modelcontextprotocol/server-slack` + `SLACK_BOT_TOKEN` |
| [Brave Search](servers/official/brave-search.md) | Web + local search via Brave API | `brave_web_search`, `brave_local_search` | `npx -y @modelcontextprotocol/server-brave-search` + `BRAVE_API_KEY` |
| [Fetch](servers/official/fetch.md) | Web page fetching + markdown conversion | `fetch`, `screenshot` | `npx -y @modelcontextprotocol/server-fetch` |
| [Playwright](servers/official/playwright.md) | Browser automation — click, fill, navigate | `navigate`, `click`, `fill`, `screenshot` | `npx -y @modelcontextprotocol/server-playwright` |

### Community

| Server | Description | Tools | Config |
|--------|-------------|-------|--------|
| [Memory](servers/community/memory.md) | Persistent key-value memory across sessions | `store_memory`, `recall_memory`, `search_memories` | `npx -y @modelcontextprotocol/server-memory` |
| [SQLite](servers/community/sqlite.md) | SQLite database query and management | `query`, `execute`, `list_tables` | `npx -y @modelcontextprotocol/server-sqlite /path/to/db` |
| [PostgreSQL](servers/community/postgres.md) | PostgreSQL database access | `query`, `execute`, `describe_table` | `npx -y @modelcontextprotocol/server-postgres` + `DATABASE_URL` |
| [Docker](servers/community/docker.md) | Container and image management | `list_containers`, `run_container`, `container_logs` | `npx -y @modelcontextprotocol/server-docker` |
| [Sentry](servers/community/sentry.md) | Error tracking and issue management | `list_issues`, `get_issue`, `search_issues` | `npx -y @modelcontextprotocol/server-sentry` + `SENTRY_AUTH_TOKEN` |
| [Invokely](servers/community/invokely.md) | Local stdio connector for Invokely's hosted official statistics service | Statistics tools and Pro workspace tools | Node 22 checkout; see local setup |

### Featured (from FreeAutomation-Tech)

| Server | Description | From |
|--------|-------------|------|
| [Agent Memory Server](servers/featured/mcp-memory-server.md) | Episodic + semantic memory MCP server | [agent-memory-kit](https://github.com/FreeAutomation-Tech/agent-memory-kit) |
| [Agent Security Server](servers/featured/mcp-security-server.md) | Input validation, output guardrails, threat scanning | [agent-security-kit](https://github.com/FreeAutomation-Tech/agent-security-kit) |

## Configurations

- [Claude Desktop](configs/claude-desktop.md) — Full config example with multiple servers
- [Custom Client](configs/custom-client.md) — Python and TypeScript client setup

## Templates

- [Python MCP Server](templates/python-server.md) — Minimal Python server template

## Guides

- [Getting Started](guides/getting-started.md) — First steps with MCP
- [Transport Options](guides/transport-options.md) — stdio vs SSE vs WebSocket

## Tooling

- [Health Check](tools/mcp-health-check.py) — Test which servers are available
- [Config Generator](tools/mcp-config-generator.py) — Generate Claude Desktop config from CLI

## Related

- [claude-marketing-kit](https://github.com/FreeAutomation-Tech/claude-marketing-kit) — Claude Marketing Skills + Python engine (copy, CRO, analytics, email, social, brand)
- [claude-seo-kit](https://github.com/FreeAutomation-Tech/claude-seo-kit) — Claude SEO Skills + Python engine (audits, schema, sitemap, hreflang, GEO)
- [agent-memory-kit](https://github.com/FreeAutomation-Tech/agent-memory-kit) — Memory patterns for AI agents
- [agent-security-kit](https://github.com/FreeAutomation-Tech/agent-security-kit) — Security patterns for AI agents
- [claude-prompt-kit](https://github.com/FreeAutomation-Tech/claude-prompt-kit) — Prompt engineering patterns

---

> If you find this useful, please consider giving it a star ⭐ on GitHub — it helps others discover these MCP servers and keeps the collection growing.

<p align="center">
  <a href="https://github.com/FreeAutomation-Tech/awesome-mcp-servers">GitHub</a> •
  <a href="https://github.com/FreeAutomation-Tech/awesome-mcp-servers/issues">Issues</a> •
  <a href="https://github.com/FreeAutomation-Tech/awesome-mcp-servers/pulls">PRs</a>
</p>

<p align="center">
  <sub>Built with ❤️ by <a href="https://github.com/FreeAutomation-Tech">FreeAutomation-Tech</a></sub>
</p>
