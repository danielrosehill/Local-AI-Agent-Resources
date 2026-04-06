# Desktop AI Agents

A curated list of **on-device AI agent runners, harnesses, and tooling** — agents whose control loop runs locally on your desktop, laptop, or workstation rather than on a hosted cloud platform.

The underlying *model* may be a hosted API (Anthropic, OpenAI, xAI, Mistral…) or a fully local engine (Ollama, llama.cpp, vLLM). What unifies this list is that **the harness lives on your machine**.

## Scope

**In scope**
- CLI / TUI coding agents you run in a repo
- Sysadmin-style agents that use your filesystem, shell, and networked resources
- Tooling that wraps, orchestrates, or manages on-device agent CLIs
- Multi-agent frameworks that execute locally
- Agent harness specifications (AGENTS.md, Skills, etc.)

**Out of scope**
- Server-deployed / cloud-hosted agent platforms
- Agents that only run as a hosted SaaS
- Pure IDE extensions where the CLI is only a companion (IDE-first tools)
- Inference engines without an agent loop

## Badge Legend

Each entry is tagged with shields.io badges. The dynamic ones (stars, last commit) update automatically from GitHub.

| Badge | Meaning |
|---|---|
| ![Type: 1st-party](https://img.shields.io/badge/Type-1st--party-blue) | Built by the model vendor (OpenAI, Anthropic, Mistral, GitHub, Moonshot, xAI…) |
| ![Type: 3rd-party](https://img.shields.io/badge/Type-3rd--party-lightgrey) | Independent / community project |
| ![Interface: CLI](https://img.shields.io/badge/UI-CLI-green) ![Interface: TUI](https://img.shields.io/badge/UI-TUI-green) ![Interface: GUI](https://img.shields.io/badge/UI-GUI-green) | Primary interface |
| ![Local: Ollama](https://img.shields.io/badge/Local-Ollama-orange) ![Local: Yes](https://img.shields.io/badge/Local-Yes-orange) ![Cloud only](https://img.shields.io/badge/Local-No-red) | Local-model support |
| ![MCP](https://img.shields.io/badge/MCP-Yes-purple) | Supports MCP (Model Context Protocol) |
| ![Tools](https://img.shields.io/badge/Tools-Yes-purple) | Supports tool use / function calling |
| ![Use: Code](https://img.shields.io/badge/Use-Code-yellow) ![Use: Sysadmin](https://img.shields.io/badge/Use-Sysadmin-yellow) | Primary use case — constrained in-repo code work vs fluid programmatic use of the machine |

> Local/MCP/Tools flags are best-effort — verify against upstream docs before relying on them.

## Table of Contents

- [1. AI Coding Agents (CLI)](#1-ai-coding-agents-cli)
  - [First-party (vendor)](#first-party-vendor)
  - [Third-party](#third-party)
- [2. Tooling Around Agent CLIs](#2-tooling-around-agent-clis)
  - [Session & Task Managers](#session--task-managers)
  - [Orchestrators](#orchestrators)
- [3. Multi-Agent Frameworks](#3-multi-agent-frameworks)
- [4. Harnesses & Specifications](#4-harnesses--specifications)
- [Contributing](#contributing)
- [Disclaimer](#disclaimer)

---

## 1. AI Coding Agents (CLI)

CLI agents designed to work inside a code repository. **In scope:** tool use, MCP support, local *or* cloud model support. **Out of scope:** GUI apps, pure inference engines, IDE-only tools where the CLI is just a companion.

### First-party (vendor)

#### [copilot-cli](https://github.com/github/copilot-cli)

![Stars](https://img.shields.io/github/stars/github/copilot-cli?style=social) ![Last commit](https://img.shields.io/github/last-commit/github/copilot-cli) ![Type](https://img.shields.io/badge/Type-1st--party-blue) ![UI](https://img.shields.io/badge/UI-CLI-green) ![Local](https://img.shields.io/badge/Local-No-red) ![Use](https://img.shields.io/badge/Use-Code-yellow)

GitHub Copilot CLI — brings the Copilot coding agent directly to your terminal.

**Language:** Shell · **Author:** [github](https://github.com/github)

---

#### [kimi-cli](https://github.com/MoonshotAI/kimi-cli)

![Stars](https://img.shields.io/github/stars/MoonshotAI/kimi-cli?style=social) ![Last commit](https://img.shields.io/github/last-commit/MoonshotAI/kimi-cli) ![Type](https://img.shields.io/badge/Type-1st--party-blue) ![UI](https://img.shields.io/badge/UI-CLI-green) ![Local](https://img.shields.io/badge/Local-No-red) ![Use](https://img.shields.io/badge/Use-Code-yellow)

Moonshot's Kimi Code CLI — vendor coding agent for the Kimi model family.

**Language:** Python · **Author:** [MoonshotAI](https://github.com/MoonshotAI)

---

#### [mistral-vibe](https://github.com/mistralai/mistral-vibe)

![Stars](https://img.shields.io/github/stars/mistralai/mistral-vibe?style=social) ![Last commit](https://img.shields.io/github/last-commit/mistralai/mistral-vibe) ![Type](https://img.shields.io/badge/Type-1st--party-blue) ![UI](https://img.shields.io/badge/UI-CLI-green) ![Local](https://img.shields.io/badge/Local-No-red) ![Use](https://img.shields.io/badge/Use-Code-yellow)

Minimal CLI coding agent by Mistral.

**Language:** Python · **Author:** [mistralai](https://github.com/mistralai)

---

### Third-party

#### [aider](https://github.com/Aider-AI/aider) · _major_

![Stars](https://img.shields.io/github/stars/Aider-AI/aider?style=social) ![Last commit](https://img.shields.io/github/last-commit/Aider-AI/aider) ![Type](https://img.shields.io/badge/Type-3rd--party-lightgrey) ![UI](https://img.shields.io/badge/UI-CLI-green) ![Local](https://img.shields.io/badge/Local-Yes-orange) ![Use](https://img.shields.io/badge/Use-Code-yellow)

AI pair programming in your terminal. Works with most major models including local ones via Ollama / LiteLLM.

**Language:** Python · **Author:** [Aider-AI](https://github.com/Aider-AI)

---

#### [Cougar-CLI](https://github.com/dulikaifazr/Cougar-CLI)

![Stars](https://img.shields.io/github/stars/dulikaifazr/Cougar-CLI?style=social) ![Last commit](https://img.shields.io/github/last-commit/dulikaifazr/Cougar-CLI) ![Type](https://img.shields.io/badge/Type-3rd--party-lightgrey) ![UI](https://img.shields.io/badge/UI-CLI-green) ![Use](https://img.shields.io/badge/Use-Code-yellow)

An AI programming agent for the command line.

**Language:** TypeScript · **Author:** [dulikaifazr](https://github.com/dulikaifazr)

---

#### [goose](https://github.com/block/goose) · _major_

![Stars](https://img.shields.io/github/stars/block/goose?style=social) ![Last commit](https://img.shields.io/github/last-commit/block/goose) ![Type](https://img.shields.io/badge/Type-3rd--party-lightgrey) ![UI](https://img.shields.io/badge/UI-CLI-green) ![MCP](https://img.shields.io/badge/MCP-Yes-purple) ![Local](https://img.shields.io/badge/Local-Yes-orange) ![Use](https://img.shields.io/badge/Use-Code-yellow) ![Use](https://img.shields.io/badge/Use-Sysadmin-yellow)

Open-source, extensible AI agent that goes beyond code suggestions — install, execute, edit, and test with any LLM. Strong MCP support, straddles code and sysadmin use cases.

**Language:** Rust · **Author:** [block](https://github.com/block)

---

#### [grok-cli](https://github.com/superagent-ai/grok-cli)

![Stars](https://img.shields.io/github/stars/superagent-ai/grok-cli?style=social) ![Last commit](https://img.shields.io/github/last-commit/superagent-ai/grok-cli) ![Type](https://img.shields.io/badge/Type-3rd--party-lightgrey) ![UI](https://img.shields.io/badge/UI-CLI-green) ![Local](https://img.shields.io/badge/Local-No-red) ![Use](https://img.shields.io/badge/Use-Code-yellow)

Open-source autonomous agent powered by Grok.

**Language:** TypeScript · **Author:** [superagent-ai](https://github.com/superagent-ai)

---

#### [hermes-agent](https://github.com/NousResearch/hermes-agent)

![Stars](https://img.shields.io/github/stars/NousResearch/hermes-agent?style=social) ![Last commit](https://img.shields.io/github/last-commit/NousResearch/hermes-agent) ![Type](https://img.shields.io/badge/Type-3rd--party-lightgrey) ![UI](https://img.shields.io/badge/UI-CLI-green)

"The agent that grows with you" — from Nous Research. Scope / in-repo vs sysadmin usage TBD.

**Language:** Python · **Author:** [NousResearch](https://github.com/NousResearch)

---

#### [OpenHands](https://github.com/OpenHands/OpenHands) · _major_

![Stars](https://img.shields.io/github/stars/OpenHands/OpenHands?style=social) ![Last commit](https://img.shields.io/github/last-commit/OpenHands/OpenHands) ![Type](https://img.shields.io/badge/Type-3rd--party-lightgrey) ![UI](https://img.shields.io/badge/UI-CLI-green) ![UI](https://img.shields.io/badge/UI-GUI-green) ![Local](https://img.shields.io/badge/Local-Yes-orange) ![Use](https://img.shields.io/badge/Use-Code-yellow)

OpenHands (formerly OpenDevin) — AI-driven development platform. Runs agents locally in a sandboxed environment, supports many model backends including local ones.

**Language:** Python · **Author:** [OpenHands](https://github.com/OpenHands)

---

#### [opencode](https://github.com/anomalyco/opencode) · _major_

![Stars](https://img.shields.io/github/stars/anomalyco/opencode?style=social) ![Last commit](https://img.shields.io/github/last-commit/anomalyco/opencode) ![Type](https://img.shields.io/badge/Type-3rd--party-lightgrey) ![UI](https://img.shields.io/badge/UI-TUI-green) ![Local](https://img.shields.io/badge/Local-Yes-orange) ![Use](https://img.shields.io/badge/Use-Code-yellow)

The open source coding agent — provider-agnostic TUI coding agent.

**Language:** TypeScript · **Author:** [anomalyco](https://github.com/anomalyco)

---

#### [pi-mono](https://github.com/badlogic/pi-mono)

![Stars](https://img.shields.io/github/stars/badlogic/pi-mono?style=social) ![Last commit](https://img.shields.io/github/last-commit/badlogic/pi-mono) ![Type](https://img.shields.io/badge/Type-3rd--party-lightgrey) ![UI](https://img.shields.io/badge/UI-CLI-green) ![Use](https://img.shields.io/badge/Use-Code-yellow)

AI agent toolkit: coding agent CLI, unified LLM API, TUI & web UI libraries, Slack bot, vLLM pods.

**Language:** TypeScript · **Author:** [badlogic](https://github.com/badlogic)

---

## 2. Tooling Around Agent CLIs

Tools that wrap, manage, or orchestrate the CLI agents above.

### Session & Task Managers

#### [ccmanager](https://github.com/kbwo/ccmanager)

![Stars](https://img.shields.io/github/stars/kbwo/ccmanager?style=social) ![Last commit](https://img.shields.io/github/last-commit/kbwo/ccmanager) ![UI](https://img.shields.io/badge/UI-TUI-green)

Coding Agent Session Manager for Claude Code / Gemini CLI / Codex CLI / Cursor Agent / Copilot CLI / Cline CLI / OpenCode / Kimi CLI.

**Language:** TypeScript · **Author:** [kbwo](https://github.com/kbwo)

---

### Orchestrators

#### [agent-browser](https://github.com/vercel-labs/agent-browser)

![Stars](https://img.shields.io/github/stars/vercel-labs/agent-browser?style=social) ![Last commit](https://img.shields.io/github/last-commit/vercel-labs/agent-browser) ![UI](https://img.shields.io/badge/UI-CLI-green)

Browser automation CLI for AI agents.

**Language:** Rust · **Author:** [vercel-labs](https://github.com/vercel-labs)

---

#### [blackbox cli](https://github.com/blackboxaicode/cli)

![Stars](https://img.shields.io/github/stars/blackboxaicode/cli?style=social) ![Last commit](https://img.shields.io/github/last-commit/blackboxaicode/cli) ![UI](https://img.shields.io/badge/UI-CLI-green)

BLACKBOX CLI for running multi-agents locally with a Judge to select the best task implementation.

**Language:** TypeScript · **Author:** [blackboxaicode](https://github.com/blackboxaicode)

---

## 3. Multi-Agent Frameworks

On-device multi-agent orchestration.

#### [agency-agents](https://github.com/msitarzewski/agency-agents)

![Stars](https://img.shields.io/github/stars/msitarzewski/agency-agents?style=social) ![Last commit](https://img.shields.io/github/last-commit/msitarzewski/agency-agents)

A complete AI agency at your fingertips — specialized expert agents with personalities, processes, and deliverables.

**Language:** Shell · **Author:** [msitarzewski](https://github.com/msitarzewski)

---

#### [wshobson/agents](https://github.com/wshobson/agents)

![Stars](https://img.shields.io/github/stars/wshobson/agents?style=social) ![Last commit](https://img.shields.io/github/last-commit/wshobson/agents)

Intelligent automation and multi-agent orchestration for Claude Code.

**Language:** Python · **Author:** [wshobson](https://github.com/wshobson)

---

## 4. Harnesses & Specifications

Open formats, specs, and framework-level harnesses that cut across individual agent CLIs.

#### [agents.md](https://github.com/agentsmd/agents.md)

![Stars](https://img.shields.io/github/stars/agentsmd/agents.md?style=social) ![Last commit](https://img.shields.io/github/last-commit/agentsmd/agents.md)

AGENTS.md — a simple, open format for guiding coding agents.

**Language:** TypeScript · **Author:** [agentsmd](https://github.com/agentsmd)

---

#### [agentskills](https://github.com/agentskills/agentskills)

![Stars](https://img.shields.io/github/stars/agentskills/agentskills?style=social) ![Last commit](https://img.shields.io/github/last-commit/agentskills/agentskills)

Specification and documentation for Agent Skills.

**Language:** Python · **Author:** [agentskills](https://github.com/agentskills)

---

#### [stakpak/agent](https://github.com/stakpak/agent)

![Stars](https://img.shields.io/github/stars/stakpak/agent?style=social) ![Last commit](https://img.shields.io/github/last-commit/stakpak/agent) ![UI](https://img.shields.io/badge/UI-CLI-green) ![Use](https://img.shields.io/badge/Use-Sysadmin-yellow)

Ship your code, on autopilot. An open source agent that lives on your machines 24/7 and keeps your apps running.

**Language:** Rust · **Author:** [stakpak](https://github.com/stakpak)

---

## Contributing

Suggestions and PRs are very welcome — especially to fill in missing badges (local-model support, MCP, vendor vs third-party). Open a PR or reach out: [public@danielrosehill.com](mailto:public@danielrosehill.com).

When adding a project, please include:

- Name + GitHub link
- Stars + last-commit badges (dynamic shields.io)
- Type badge: 1st-party or 3rd-party
- Interface badge: CLI / TUI / GUI
- Local-model support (Ollama / Yes / No)
- MCP + tool-use badges where applicable
- Use-case badge: Code / Sysadmin
- 1–2 sentence description, language, author link

## Disclaimer

This list is **non-exhaustive** and best-effort. Inclusion is not an endorsement, exclusion is not a judgment. The on-device agent space is moving fast — expect gaps, staleness, and occasional mis-classification. Verify capability claims (especially local-model and MCP support) against upstream docs.

---

Maintained by [Daniel Rosehill](https://danielrosehill.com)
