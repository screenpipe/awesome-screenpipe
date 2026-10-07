# Awesome Screenpipe [![Awesome](https://awesome.re/badge.svg)](https://awesome.re)

> A curated list of resources, integrations, pipes, and community projects for [Screenpipe](https://screenpi.pe): AI that knows everything you've seen, said, or heard.

Screenpipe captures screen text and audio locally while recording is enabled, making computer history searchable for people and AI assistants. Its source is available under the [Screenpipe Commercial License](https://github.com/screenpipe/screenpipe/blob/main/LICENSE.md), not an open-source license. Optional cloud AI, transcription, sync, and connected services can transmit context off-device; see the [privacy data flow](https://docs.screenpipe.com/privacy-data-flow).

## Contents

- [Official Resources](#official-resources)
- [Official Libraries](#official-libraries)
- [Scheduled tasks and pipes](#scheduled-tasks-and-pipes)
- [MCP Server](#mcp-server)
- [AI Coding Tool Integrations](#ai-coding-tool-integrations)
- [Community Projects](#community-projects)
  - [Notes and personal memory](#notes-and-personal-memory)
  - [Dashboards and desktop tools](#dashboards-and-desktop-tools)
  - [Workflow integrations](#workflow-integrations)
  - [Clients and developer tools](#clients-and-developer-tools)
  - [Hackathon prototypes](#hackathon-prototypes)
- [Hackathons and starter projects](#hackathons-and-starter-projects)
- [Service Integrations](#service-integrations)
- [Tutorials & Articles](#tutorials--articles)
- [Research and experiments](#research-and-experiments)

## Official Resources

- [Screenpipe](https://github.com/screenpipe/screenpipe): Main repository (desktop app + CLI)
- [Documentation](https://docs.screenpi.pe): Official docs
- [API reference](https://docs.screenpi.pe/llms-full.txt): Documentation in a single text file for API users and agents
- [API recipes](https://docs.screenpipe.com/api-recipes): Authenticated examples for search, meetings, frames, and memory
- [CLI reference](https://docs.screenpipe.com/cli-reference): Recording, search, agent setup, and pipe commands
- [Scheduled Task Guide](https://docs.screenpipe.com/scheduled-tasks): Build custom pipes
- [Discord](https://discord.gg/screenpipe): Community chat
- [Resource library](https://screenpipe.com/resources): Official use cases and integration guides

## Official Libraries

- [screenpipe/uniOCR](https://github.com/screenpipe/uniOCR): Native OCR for macOS, Windows, Linux
- [screenpipe/audiopipe](https://github.com/screenpipe/audiopipe): Fast speech-to-text in Rust (Qwen3-ASR, CoreML, DirectML, CUDA)
- [screenpipe-mcp](https://www.npmjs.com/package/screenpipe-mcp): MCP server npm package; see [setup instructions](https://github.com/screenpipe/screenpipe/tree/main/packages/screenpipe-mcp#installation)
- [Screenpipe Swift SDK](https://github.com/screenpipe/screenpipe-sdk-swift): Swift Package Manager distribution for embedding capture in macOS apps; enterprise license and runtime requirements apply
- [sck-rs](https://github.com/screenpipe/sck-rs): Rust screen capture library using Apple's ScreenCaptureKit

## Scheduled tasks and pipes

The app calls pipes **Scheduled tasks**. They are AI automations defined with a prompt and schedule; the CLI still uses `screenpipe pipe` and `pipe.md`. Browse them under **Scheduled tasks > Discover**.

- [Task library](https://docs.screenpipe.com/task-library): Available automations, including Obsidian sync, meeting intelligence, and time tracking
- [Build scheduled tasks](https://docs.screenpipe.com/scheduled-tasks): Write and configure your own pipe
- [Reliable reports](https://docs.screenpipe.com/reliable-reports): Define source windows, verify saved output, and check reruns before scheduling
- [Task permissions](https://docs.screenpipe.com/task-permissions): Scope the captured data a task can access
- [Task troubleshooting](https://docs.screenpipe.com/task-troubleshooting): Diagnose failed runs and missing output

## MCP Server

Screenpipe exposes an [MCP (Model Context Protocol)](https://modelcontextprotocol.io/) server for retrieving recorded context and managing supported actions. Use **Settings > Connections** in the desktop app for the recommended setup: it configures the bundled runtime and `SCREENPIPE_LOCAL_API_KEY`. Manual setup requires a running Screenpipe instance; follow the [official MCP installation guide](https://github.com/screenpipe/screenpipe/tree/main/packages/screenpipe-mcp#installation). Retrieved context is available to the connected assistant and its configured model provider.

### Compatible Clients

- [Claude Desktop](https://claude.ai/download): Anthropic's desktop app
- [Claude Code](https://docs.anthropic.com/en/docs/claude-code): CLI coding assistant
- [Cursor](https://cursor.com): AI code editor
- [VS Code + Cline](https://github.com/cline/cline): Autonomous coding agent for VS Code
- [VS Code + Continue](https://continue.dev): Open-source AI code assistant
- [Codex](https://screenpipe.com/integrations/codex): Screenpipe setup for the Codex app and CLI
- Any MCP-compatible client

## AI Coding Tool Integrations

Use these Screenpipe-specific setup guides to connect your assistant to recorded context:

- [Codex](https://screenpipe.com/integrations/codex): Desktop and CLI integration
- [Claude Code](https://docs.screenpipe.com/claude-code): MCP setup and work-history queries
- [Cline](https://docs.screenpipe.com/cline): Screenpipe context inside VS Code
- [Continue](https://docs.screenpipe.com/continue): MCP connection for the coding assistant
- [OpenCode](https://docs.screenpipe.com/opencode): Screenpipe MCP configuration
- [Gemini CLI extension](https://github.com/screenpipe/gemini-cli-extension): MCP server and a skill for workflow recall and cited procedures
- [GitHub Copilot CLI](https://docs.screenpipe.com/copilot-cli): Screen history and meeting context in the terminal
- [OpenClaw](https://docs.screenpipe.com/openclaw): Connect Screenpipe memory to the personal assistant
- [Hermes](https://docs.screenpipe.com/hermes): MCP and skills for recall, meeting preparation, and worklogs
- [Screenpipe Cloud](https://github.com/screenpipe/screenpipe-cloud): Read-only plugin for searching records already uploaded through Data Sync from Claude, ChatGPT, and Codex; requires Data Sync access

## Community Projects

Descriptions below are based on each project's public documentation, checked October 7, 2026. These are independently maintained projects; current Screenpipe compatibility has not been runtime-tested. Check each project's setup, license, and model-provider requirements.

### Notes and personal memory

- [Note Companion](https://github.com/Nexus-JPF/note-companion): Obsidian plugin with a Screenpipe integration for meeting notes and activity search
- [Screenpipe Obsidian Go](https://github.com/nii236/screenpipe-obsidian-go): Go service that turns Screenpipe activity into Obsidian work logs and daily summaries using OpenAI
- [Screenpipe Distiller](https://github.com/marcelsamyn/screenpipe-distiller): Condenses daily capture into a Markdown memory document using OpenRouter and uploads it to a compatible memory backend
- [Zelin's AI Assistant](https://github.com/Wan-ZL/zelin-ai-assistant): Exports Screenpipe context to an Obsidian wiki and turns incoming requests into approval cards for Claude agents
- [Agentic Cortex](https://github.com/albert-ying/agentic-cortex): Personal assistant framework combining structured Markdown memory, Screenpipe context, and OpenClaw or Claude Code

### Dashboards and desktop tools

- [Ghostwork](https://github.com/hvardhan878/ghostwork): Community GUI with a Screenpipe timeline, app-usage analytics, and macOS workflow automation
- [Screenpipe Dashboard](https://github.com/yujiachen-y/screenpipe-dashboard): macOS menu bar status and a timeline viewer for screenshots, OCR, and audio transcripts
- [Screenpipe Manager](https://github.com/acyclic-eu/screenpipe-manager): macOS recording controls and a local web dashboard with search and screenshot thumbnails
- [Screenpipe Raycast](https://github.com/neo773/screenpipe-raycast): Raycast extension for managing pipes; built for the earlier pipe system

### Workflow integrations

- [WorkToJiraEffort](https://github.com/UltraInstinct0x/WorkToJiraEffort): Detects Jira issue keys in captured activity and logs work time to Jira, with optional Salesforce entries
- [Stream Deck Workflow Advisor](https://github.com/vasceannie/screenpipe-streamdeck-mcp): Pipe that recommends Stream Deck actions, plugins, and layouts from recent desktop activity
- [kordi Subscription Finder](https://github.com/kordi-labs/kordi-screenpipe-pipe): Pipe that finds billing signals in screen text and sends subscription records to kordi
- [focuspipe](https://github.com/pleasedodisturb/focuspipe): Focus and context-switch tracking pipes with Goose integration, session summaries, and configurable nudges
- [Screenpipe Plugins](https://github.com/fhorn97/screenpipe-plugins): Next.js pipe examples for meeting summaries, Notion sync, and Reddit posting, using the earlier pipe architecture

### Clients and developer tools

- [Screenpipe Python Client](https://github.com/TanGentleman/screenpipe-python-client): Python client for exploring and debugging Screenpipe's API
- [Screenpipe SDK for Rust](https://github.com/heavenly/screenpipe-sdk-rs): Experimental community API wrapper; the author notes that most functions were not tested

### Hackathon prototypes

These projects are useful examples to inspect and adapt. Their original setup may need updates for current Screenpipe versions.

- [Meeting Maestro](https://github.com/Glavin001/screenpipe-meeting-assistant): Live meeting transcripts organized against predefined questions; additional question suggestions are listed as unfinished
- [AI Interview Coach](https://github.com/KentTDang/AI-Interview-Coach): Interview practice combining Screenpipe audio context, answer evaluation, and MediaPipe body-language tracking
- [Screen Time Wrapped](https://github.com/andrewchu16/screentime-wrapped): Gemini-generated slides about the previous day's app and website usage
- [Screen Productivity Tracker](https://github.com/arice77/activity-todo-screenpipe): Activity dashboard and Gemini-powered todo suggestions from captured work
- [baseballwalkerchris/screenpipe-hackathon](https://github.com/baseballwalkerchris/screenpipe-hackathon): Community hackathon repository
- [Bright Path](https://devpost.com/software/bright-path-81pk03): Hackathon learning assistant using Screenpipe screen context and Gemini to help with educational tasks
- [Lenz](https://devpost.com/software/lenz): Hackathon reading assistant bridging Screenpipe OCR and CrewAI through an MCP server
- [wzrd.work](https://devpost.com/software/wzrd-work): Hackathon workflow-capture prototype combining Screenpipe with computer-use and conversational tools

### Integration requests in other projects

These are proposals, not evidence of a shipped integration.

- [PrivateGPT: Screenpipe integration](https://github.com/zylon-ai/private-gpt/issues/2200): Closed proposal for local screen/audio context
- [Aider: Screenpipe for screen context](https://github.com/Aider-AI/aider/issues/4800): Proposal for coding-session context

## Hackathons and starter projects

- [Build Agents That Remember @42Paris](https://luma.com/bnre6nou): October 16–18, 2026, at École 42 Paris, organized by 42Entrepreneurs and Screenpipe. Tracks cover finding work to automate, teaching agents workflows, and making automations work for a team
- [Screenpipe hackathon starter](https://github.com/screenpipe/hackathon-starter): Runnable examples for work-session SOPs, workflow review and replay, support escalation, handoffs, evidence search, and repeated-task discovery, with fictional sample data and tests; sample mode needs no AI key or Screenpipe installation
- [Screenpipe Agentic Hackathon](https://www.sprint.dev/hackathons/screenpipe): Earlier Screenpipe agent-building event on Sprint.dev

## Service Integrations

Use the [connections guide](https://docs.screenpipe.com/connections) and [connection reference](https://docs.screenpipe.com/connection-reference) for the current registry, authentication methods, and setup. Availability and account requirements vary by service.

| Category | Examples |
| --- | --- |
| Communication | Slack, Discord, Telegram, Gmail, Outlook, Microsoft Teams |
| Notes and documents | Notion, Obsidian, Google Docs, Google Drive, Logseq |
| Project management | Linear, Jira, Asana, Todoist |
| CRM and support | HubSpot, Salesforce, Pipedrive, Intercom, Zendesk |
| Developer tools | GitHub, Sentry, Vercel, Supabase, PostHog |
| Automation | n8n, Make, Zapier, Pushover, ntfy |

## Tutorials & Articles

- [Build a second brain](https://docs.screenpipe.com/second-brain): Official guide to organizing captured context into personal knowledge
- [Screenpipe Blog](https://screenpi.pe/blog): Official blog with guides and updates
- [Screenpipe Docs: Getting Started](https://docs.screenpipe.com/getting-started): Quick start guide

### Practical workflow guides

- [Meeting intelligence](https://docs.screenpipe.com/meeting-intelligence): Transcripts, speaker context, and meeting summaries
- [Obsidian integration](https://docs.screenpipe.com/obsidian): Query Screenpipe history from an Obsidian AI plugin
- [Workflow discovery](https://docs.screenpipe.com/workflow-discovery): Find repeated tasks in recorded work
- [Team SOP capture](https://docs.screenpipe.com/team-sop-capture): Turn captured work into procedures for review
- [Local or cloud AI](https://docs.screenpipe.com/local-or-cloud-ai): Choose where model processing happens
- [Ollama](https://docs.screenpipe.com/ollama): Configure local models with Screenpipe

## Research and experiments

- [ScreenLeak](https://github.com/screenpipe/screenleak): Benchmark for sensitive-information redaction in screen text, screenshots, and computer-use traces
- [River AI + Screenpipe training](https://github.com/screenpipe/river-ai-screenpipe-training): Experimental toolkit for curating selected chats and Screenpipe context into reviewed training data, running River fine-tuning, and evaluating results

## Contributing

Contributions welcome! Include a public project URL and a short description of how it uses Screenpipe. Prefer the author's repository, documentation, or demo. Label prototypes and integration proposals, and note any required cloud service or paid account. Avoid duplicate listings and unrelated tools that only mention Screenpipe.

If you've built something with Screenpipe, please open a PR to add it here.

## License

[![CC0](https://licensebuttons.net/p/zero/1.0/88x31.png)](https://creativecommons.org/publicdomain/zero/1.0/)
