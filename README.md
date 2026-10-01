# Awesome Screenpipe [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated list of resources, integrations, pipes, and community projects for [Screenpipe](https://screenpi.pe) — AI that knows everything you've seen, said, or heard.

Screenpipe captures screen text and audio locally while recording is enabled, making computer history searchable for people and AI assistants. Its source is available under the [Screenpipe Commercial License](https://github.com/screenpipe/screenpipe/blob/main/LICENSE.md), not an open-source license. Optional cloud AI, transcription, sync, and connected services can transmit context off-device; see the [privacy data flow](https://docs.screenpipe.com/privacy-data-flow).

## Contents

- [Official Resources](#official-resources)
- [Official Libraries](#official-libraries)
- [Built-in Pipes](#built-in-pipes)
- [MCP Server](#mcp-server)
- [AI Coding Tool Integrations](#ai-coding-tool-integrations)
- [Community Projects](#community-projects)
- [Service Integrations](#service-integrations)
- [Tutorials & Articles](#tutorials--articles)

## Official Resources

- [Screenpipe](https://github.com/screenpipe/screenpipe) — Main repository (desktop app + CLI)
- [Documentation](https://docs.screenpi.pe) — Official docs
- [API Reference](https://docs.screenpi.pe/llms-full.txt) — Full REST API reference (60+ endpoints)
- [Scheduled Task Guide](https://docs.screenpipe.com/scheduled-tasks) — Build custom pipes
- [Discord](https://discord.gg/screenpipe) — Community chat

## Official Libraries

- [screenpipe/uniOCR](https://github.com/screenpipe/uniOCR) — Native OCR for macOS, Windows, Linux
- [screenpipe/audiopipe](https://github.com/screenpipe/audiopipe) — Fast speech-to-text in Rust (Qwen3-ASR, CoreML, DirectML, CUDA)
- [screenpipe-mcp](https://www.npmjs.com/package/screenpipe-mcp) — MCP server npm package; see [setup instructions](https://github.com/screenpipe/screenpipe/tree/main/packages/screenpipe-mcp#installation)

## Built-in Pipes

Pipes are plugins that run inside Screenpipe and process your captured data.

- **Obsidian Sync** — Automatically sync screen activity and meeting notes to your Obsidian vault
- **Notion Integration** — Push captured data and summaries to Notion
- **Meeting Notes** — Auto-generate meeting summaries from audio transcriptions (Zoom, Google Meet, Teams, Webex)
- **Pipe Store** — Browse and install pipes from the in-app store

## MCP Server

Screenpipe exposes an [MCP (Model Context Protocol)](https://modelcontextprotocol.io/) server for retrieving recorded context and managing supported actions. Use **Settings > Connections** in the desktop app for the recommended setup: it configures the bundled runtime and `SCREENPIPE_LOCAL_API_KEY`. Manual setup requires a running Screenpipe instance; follow the [official MCP installation guide](https://github.com/screenpipe/screenpipe/tree/main/packages/screenpipe-mcp#installation). Retrieved context is available to the connected assistant and its configured model provider.

### Compatible Clients

- [Claude Desktop](https://claude.ai/download) — Anthropic's desktop app
- [Claude Code](https://docs.anthropic.com/en/docs/claude-code) — CLI coding assistant
- [Cursor](https://cursor.com) — AI code editor
- [VS Code + Cline](https://github.com/cline/cline) — Autonomous coding agent for VS Code
- [VS Code + Continue](https://continue.dev) — Open-source AI code assistant
- [Windsurf](https://codeium.com/windsurf) — AI IDE by Codeium
- Any MCP-compatible client

### MCP Listings

- [mcpindex.net](https://mcpindex.net) — MCP server directory
- [pulsemcp.com](https://pulsemcp.com) — MCP server catalog
- [topmcp.org](https://topmcp.org) — MCP server rankings

## AI Coding Tool Integrations

Screenpipe works with AI coding tools via MCP or direct API access:

- **Cursor** — Add Screenpipe MCP server in Cursor settings
- **Claude Code** — Configure as MCP server in `~/.claude.json`
- **Cline** — Add as MCP server in Cline extension settings
- **Continue** — Configure via Continue's MCP support
- **OpenCode** — MCP server integration
- **Gemini CLI** — Use via MCP or REST API

## Community Projects

- [Different AI / Note Companion](https://github.com/different-ai/note-companion) — Obsidian plugin with Screenpipe integration for AI-powered meeting notes and screen activity search
- [TanGentleman/screenpipe-python-client](https://github.com/TanGentleman/screenpipe-python-client) — Python client to debug and interact with Screenpipe's API
- [baseballwalkerchris/screenpipe-hackathon](https://github.com/baseballwalkerchris/screenpipe-hackathon) — Hackathon project built on Screenpipe

### Integration Requests in Other Projects

- [PrivateGPT — Screenpipe integration](https://github.com/zylon-ai/private-gpt/issues/2200) — Proposed integration for local screen/audio context
- [Aider — Screenpipe for screen context](https://github.com/Aider-AI/aider/issues/4800) — Proposed integration for coding session context

### Hackathons

- [Screenpipe hackathon starter](https://github.com/screenpipe/hackathon-starter): nine Bun projects covering SOP drafts, workflow review, bounded replay, support escalation, shift handoffs, evidence search, SOP comparisons, onboarding and repeated-task discovery. Includes runnable fictional demos, sample outputs and acceptance tests; no AI key is required for sample mode.
- [Screenpipe Agentic Hackathon](https://www.sprint.dev/hackathons/screenpipe) — LLM agent projects built on Screenpipe (Sprint.dev)

## Service Integrations

Screenpipe connects to external services via the Settings > Connections panel:

- **Telegram** — Send notifications and summaries via bot
- **Slack** — Post to channels via webhook
- **Discord** — Send messages via webhook
- **Email** — SMTP-based email notifications
- **Todoist** — Create tasks from screen activity
- **Microsoft Teams** — Post via webhook

### CRM & Sales (via Pipes)

- Salesforce
- HubSpot
- Pipedrive
- LinkedIn

## Tutorials & Articles

- [Building a Personal Knowledge Management System with Screenpipe](https://dev.to/medsonmoombe/building-a-personal-knowledge-management-system-with-screenpipe-48ch) — DEV.to tutorial
- [Screenpipe Blog](https://screenpi.pe/blog) — Official blog with guides and updates
- [Screenpipe Docs — Getting Started](https://docs.screenpipe.com/getting-started) — Quick start guide

## Contributing

Contributions welcome! Include the project URL and a short description of how it integrates with Screenpipe.

If you've built something with Screenpipe, please open a PR to add it here.

## License

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)
