# Desktop AI Agents

A curated list of **on-device AI agent runners, harnesses, and tooling** — agents whose control loop runs locally on your desktop, laptop, or workstation rather than on a hosted cloud platform.

The underlying *model* may be a hosted API (Anthropic, OpenAI, xAI, Mistral…) or a fully local engine (Ollama, llama.cpp, vLLM). What unifies this list is that **the harness lives on your machine**.

## Scope

See [SCOPE.md](./SCOPE.md) for the full inclusion/exclusion rules and grey-area guidance. In short:

**In scope:** CLI/TUI coding agents, sysadmin-style agents, tooling/orchestrators around agent CLIs, MCP servers, multi-agent frameworks that run locally, computer-use agents, desktop GUI agents, personal AI assistants, terminal assistants, harnesses, and desktop-agent protocols.

**Out of scope:** cloud-hosted agent platforms, IDE-first tools where the CLI is only a companion, pure inference engines (Ollama, llama.cpp, vLLM) without an agent loop, and frameworks that don't support tool use / MCP directly.

## Badge Legend

Each entry is tagged with shields.io badges. Stars and last-commit update dynamically from GitHub.

| Badge | Meaning |
|---|---|
| ![Type: 1st-party](https://img.shields.io/badge/Type-1st--party-blue) | Built by the model vendor (OpenAI, Anthropic, Mistral, GitHub, Moonshot, xAI…) |
| ![Type: 3rd-party](https://img.shields.io/badge/Type-3rd--party-lightgrey) | Independent / community project |
| ![Interface: CLI](https://img.shields.io/badge/UI-CLI-green) ![Interface: TUI](https://img.shields.io/badge/UI-TUI-green) ![Interface: GUI](https://img.shields.io/badge/UI-GUI-green) | Primary interface |
| ![Local: Ollama](https://img.shields.io/badge/Local-Ollama-orange) ![Local: Yes](https://img.shields.io/badge/Local-Yes-orange) ![Cloud only](https://img.shields.io/badge/Local-No-red) | Local-model support |
| ![MCP](https://img.shields.io/badge/MCP-Yes-purple) | Supports MCP (Model Context Protocol) |
| ![Tools](https://img.shields.io/badge/Tools-Yes-purple) | Supports tool use / function calling |
| ![Use: Code](https://img.shields.io/badge/Use-Code-yellow) ![Use: Sysadmin](https://img.shields.io/badge/Use-Sysadmin-yellow) | Primary use case |

> Capability badges (Local/MCP/Tools) are best-effort — verify against upstream docs before relying on them.

## Table of Contents

- [1. AI Coding Agents (CLI)](#1-ai-coding-agents-cli)
- [2. Tooling Around Agent CLIs](#2-tooling-around-agent-clis)
- [3. Multi-Agent Frameworks](#3-multi-agent-frameworks)
- [4. Harnesses & Specifications](#4-harnesses--specifications)
- [5. Computer-Use & Agent Operating Systems](#5-computer-use--agent-operating-systems)
- [6. Desktop GUIs & Cowork Clones](#6-desktop-guis--cowork-clones)
- [7. Personal AI Assistants](#7-personal-ai-assistants)
- [8. Terminal Assistants](#8-terminal-assistants)
- [9. Protocols](#9-protocols)
- [10. Wallets & Payments](#10-wallets--payments)
- [11. Skill Collections](#11-skill-collections)
- [12. Voice & Speech Agents](#12-voice--speech-agents)
- [13. Remote Access & Mobile UIs](#13-remote-access--mobile-uis)
- [14. Memory](#14-memory)
- [15. Gateways & Proxies](#15-gateways--proxies)
- [16. Browser Extensions & Web Agents](#16-browser-extensions--web-agents)
- [17. Research Assistants](#17-research-assistants)
- [Related Resource Lists](#related-resource-lists)
- [Contributing](#contributing)
- [Disclaimer](#disclaimer)

---

## 1. AI Coding Agents (CLI)

CLI agents designed to work inside a code repository. **In scope:** tool use, MCP support, local *or* cloud model support. **Out of scope:** GUI apps, pure inference engines, IDE-only tools where the CLI is just a companion.

### First-party (vendor)

#### [codex](https://github.com/openai/codex)

![Stars](https://img.shields.io/github/stars/openai/codex?style=social) ![Last commit](https://img.shields.io/github/last-commit/openai/codex) ![Type](https://img.shields.io/badge/Type-1st--party-blue) ![UI](https://img.shields.io/badge/UI-CLI-green) ![Local](https://img.shields.io/badge/Local-No-red) ![Use](https://img.shields.io/badge/Use-Code-yellow)

OpenAI's lightweight coding agent that runs in your terminal.

**Language:** Rust · **Author:** [openai](https://github.com/openai)

---

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

#### [crush](https://github.com/charmbracelet/crush)

![Stars](https://img.shields.io/github/stars/charmbracelet/crush?style=social) ![Last commit](https://img.shields.io/github/last-commit/charmbracelet/crush) ![Type](https://img.shields.io/badge/Type-3rd--party-lightgrey) ![UI](https://img.shields.io/badge/UI-TUI-green) ![Use](https://img.shields.io/badge/Use-Code-yellow)

Glamourous agentic coding for all — Charm's Bubble Tea-powered TUI coding agent.

**Language:** Go · **Author:** [charmbracelet](https://github.com/charmbracelet)

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

#### [open-swe](https://github.com/langchain-ai/open-swe)

![Stars](https://img.shields.io/github/stars/langchain-ai/open-swe?style=social) ![Last commit](https://img.shields.io/github/last-commit/langchain-ai/open-swe) ![Type](https://img.shields.io/badge/Type-3rd--party-lightgrey) ![Use](https://img.shields.io/badge/Use-Code-yellow)

An open-source asynchronous coding agent from the LangChain team.

---

#### [pi-mono](https://github.com/badlogic/pi-mono)

![Stars](https://img.shields.io/github/stars/badlogic/pi-mono?style=social) ![Last commit](https://img.shields.io/github/last-commit/badlogic/pi-mono) ![Type](https://img.shields.io/badge/Type-3rd--party-lightgrey) ![UI](https://img.shields.io/badge/UI-CLI-green) ![Use](https://img.shields.io/badge/Use-Code-yellow)

AI agent toolkit: coding agent CLI, unified LLM API, TUI & web UI libraries, Slack bot, vLLM pods.

**Language:** TypeScript · **Author:** [badlogic](https://github.com/badlogic)

---

#### [trae-agent](https://github.com/bytedance/trae-agent)

![Stars](https://img.shields.io/github/stars/bytedance/trae-agent?style=social) ![Last commit](https://img.shields.io/github/last-commit/bytedance/trae-agent) ![Type](https://img.shields.io/badge/Type-3rd--party-lightgrey) ![UI](https://img.shields.io/badge/UI-CLI-green) ![Use](https://img.shields.io/badge/Use-Code-yellow)

LLM-based agent for general-purpose software engineering tasks, by ByteDance.

**Language:** Python · **Author:** [bytedance](https://github.com/bytedance)

---

## 2. Tooling Around Agent CLIs

Tools that wrap, manage, orchestrate, or extend the CLI agents above.

### Session & Task Managers

#### [agentsview](https://github.com/wesm/agentsview)

![Stars](https://img.shields.io/github/stars/wesm/agentsview?style=social) ![Last commit](https://img.shields.io/github/last-commit/wesm/agentsview) ![UI](https://img.shields.io/badge/UI-GUI-green)

Local-first desktop and web app for browsing, searching, and analyzing AI agent coding sessions across Claude Code, Codex, Gemini, OpenCode, Copilot, and more.

**Language:** Go · **Author:** [wesm](https://github.com/wesm)

---

#### [ai-helpers](https://github.com/openshift-eng/ai-helpers)

![Stars](https://img.shields.io/github/stars/openshift-eng/ai-helpers?style=social) ![Last commit](https://img.shields.io/github/last-commit/openshift-eng/ai-helpers)

Developer productivity tools for Claude Code and other AI assistants.

**Language:** Python · **Author:** [openshift-eng](https://github.com/openshift-eng)

---

#### [ccmanager](https://github.com/kbwo/ccmanager)

![Stars](https://img.shields.io/github/stars/kbwo/ccmanager?style=social) ![Last commit](https://img.shields.io/github/last-commit/kbwo/ccmanager) ![UI](https://img.shields.io/badge/UI-TUI-green)

Coding Agent Session Manager for Claude Code / Gemini CLI / Codex CLI / Cursor Agent / Copilot CLI / Cline CLI / OpenCode / Kimi CLI.

**Language:** TypeScript · **Author:** [kbwo](https://github.com/kbwo)

---

#### [codex-switcher](https://github.com/Lampese/codex-switcher)

![Stars](https://img.shields.io/github/stars/Lampese/codex-switcher?style=social) ![Last commit](https://img.shields.io/github/last-commit/Lampese/codex-switcher) ![UI](https://img.shields.io/badge/UI-GUI-green)

Desktop application for managing multiple OpenAI Codex CLI accounts.

**Language:** Rust · **Author:** [Lampese](https://github.com/Lampese)

---

#### [mux](https://github.com/coder/mux)

![Stars](https://img.shields.io/github/stars/coder/mux?style=social) ![Last commit](https://img.shields.io/github/last-commit/coder/mux) ![UI](https://img.shields.io/badge/UI-GUI-green)

A desktop app for isolated, parallel agentic development, from Coder.

**Language:** TypeScript · **Author:** [coder](https://github.com/coder)

---

#### [Vibe Kanban](https://github.com/BloopAI/vibe-kanban)

![Stars](https://img.shields.io/github/stars/BloopAI/vibe-kanban?style=social) ![Last commit](https://img.shields.io/github/last-commit/BloopAI/vibe-kanban)

Kanban-style task manager for orchestrating Claude Code, Codex, and other coding agents — get more out of any agent CLI.

---

### Orchestrators

#### [AgentChattr](https://github.com/bcurts/agentchattr)

![Stars](https://img.shields.io/github/stars/bcurts/agentchattr?style=social) ![Last commit](https://img.shields.io/github/last-commit/bcurts/agentchattr) ![Local](https://img.shields.io/badge/Local-Yes-orange)

Free, local chat where AI coding agents can tag each other, talk, and coordinate alongside the human.

---

#### [AgentFlow](https://github.com/shouc/agentflow)

![Stars](https://img.shields.io/github/stars/shouc/agentflow?style=social) ![Last commit](https://img.shields.io/github/last-commit/shouc/agentflow)

Programmatically orchestrate thousands of agents and harnesses as a graph.

---

#### [agent-orchestrator](https://github.com/ComposioHQ/agent-orchestrator)

![Stars](https://img.shields.io/github/stars/ComposioHQ/agent-orchestrator?style=social) ![Last commit](https://img.shields.io/github/last-commit/ComposioHQ/agent-orchestrator)

Agentic orchestrator for parallel coding agents — plans tasks, spawns agents, and handles CI fixes, merge conflicts, and code reviews.

**Language:** TypeScript · **Author:** [ComposioHQ](https://github.com/ComposioHQ)

---

#### [blackbox cli](https://github.com/blackboxaicode/cli)

![Stars](https://img.shields.io/github/stars/blackboxaicode/cli?style=social) ![Last commit](https://img.shields.io/github/last-commit/blackboxaicode/cli) ![UI](https://img.shields.io/badge/UI-CLI-green)

BLACKBOX CLI for running multi-agents locally with a Judge to select the best task implementation.

**Language:** TypeScript · **Author:** [blackboxaicode](https://github.com/blackboxaicode)

---

#### [helix](https://github.com/helixml/helix)

![Stars](https://img.shields.io/github/stars/helixml/helix?style=social) ![Last commit](https://img.shields.io/github/last-commit/helixml/helix) ![Local](https://img.shields.io/badge/Local-Yes-orange)

Private Agent Fleet with Spec Coding — each agent gets its own GPU-accelerated desktop. Runs Claude, Codex, Gemini, and open models on a full private AI stack.

**Language:** Go · **Author:** [helixml](https://github.com/helixml)

---

### Tools & MCP Servers

#### [AgentFS](https://github.com/tursodatabase/agentfs)

![Stars](https://img.shields.io/github/stars/tursodatabase/agentfs?style=social) ![Last commit](https://img.shields.io/github/last-commit/tursodatabase/agentfs)

A filesystem designed for agents, from the Turso team.

---

#### [chrome-devtools-mcp](https://github.com/ChromeDevTools/chrome-devtools-mcp)

![Stars](https://img.shields.io/github/stars/ChromeDevTools/chrome-devtools-mcp?style=social) ![Last commit](https://img.shields.io/github/last-commit/ChromeDevTools/chrome-devtools-mcp) ![MCP](https://img.shields.io/badge/MCP-Yes-purple)

Chrome DevTools for coding agents — exposes browser debugging to agents via MCP.

**Language:** TypeScript · **Author:** [ChromeDevTools](https://github.com/ChromeDevTools)

---

#### [DesktopCommanderMCP](https://github.com/wonderwhy-er/DesktopCommanderMCP)

![Stars](https://img.shields.io/github/stars/wonderwhy-er/DesktopCommanderMCP?style=social) ![Last commit](https://img.shields.io/github/last-commit/wonderwhy-er/DesktopCommanderMCP) ![MCP](https://img.shields.io/badge/MCP-Yes-purple) ![Use](https://img.shields.io/badge/Use-Sysadmin-yellow)

MCP server giving Claude terminal control, filesystem search, and diff-file editing.

**Language:** TypeScript · **Author:** [wonderwhy-er](https://github.com/wonderwhy-er)

---

#### [Skill Scanner](https://github.com/cisco-ai-defense/skill-scanner)

![Stars](https://img.shields.io/github/stars/cisco-ai-defense/skill-scanner?style=social) ![Last commit](https://img.shields.io/github/last-commit/cisco-ai-defense/skill-scanner)

Security scanner for Agent Skills, from Cisco AI Defense.

---

### Context & Data Access

#### [Agent-Reach](https://github.com/Panniantong/Agent-Reach)

![Stars](https://img.shields.io/github/stars/Panniantong/Agent-Reach?style=social) ![Last commit](https://img.shields.io/github/last-commit/Panniantong/Agent-Reach) ![UI](https://img.shields.io/badge/UI-CLI-green)

Give your AI agent eyes on the internet — read and search Twitter, Reddit, YouTube, GitHub, Bilibili, XiaoHongShu from one CLI.

**Language:** Python · **Author:** [Panniantong](https://github.com/Panniantong)

---

#### [agent-browser](https://github.com/vercel-labs/agent-browser)

![Stars](https://img.shields.io/github/stars/vercel-labs/agent-browser?style=social) ![Last commit](https://img.shields.io/github/last-commit/vercel-labs/agent-browser) ![UI](https://img.shields.io/badge/UI-CLI-green)

Browser automation CLI for AI agents.

**Language:** Rust · **Author:** [vercel-labs](https://github.com/vercel-labs)

---

## 3. Multi-Agent Frameworks

On-device multi-agent orchestration.

#### [agency-agents](https://github.com/msitarzewski/agency-agents)

![Stars](https://img.shields.io/github/stars/msitarzewski/agency-agents?style=social) ![Last commit](https://img.shields.io/github/last-commit/msitarzewski/agency-agents)

A complete AI agency at your fingertips — specialized expert agents with personalities, processes, and deliverables.

**Language:** Shell · **Author:** [msitarzewski](https://github.com/msitarzewski)

---

#### [Agency Swarm](https://github.com/VRSEN/agency-swarm)

![Stars](https://img.shields.io/github/stars/VRSEN/agency-swarm?style=social) ![Last commit](https://img.shields.io/github/last-commit/VRSEN/agency-swarm)

A reliable multi-agent orchestration framework.

---

#### [Aurogen](https://github.com/UniRound-Tec/Aurogen)

![Stars](https://img.shields.io/github/stars/UniRound-Tec/Aurogen?style=social) ![Last commit](https://img.shields.io/github/last-commit/UniRound-Tec/Aurogen)

The multi-agent evolution of OpenClaw.

---

#### [hive](https://github.com/aden-hive/hive)

![Stars](https://img.shields.io/github/stars/aden-hive/hive?style=social) ![Last commit](https://img.shields.io/github/last-commit/aden-hive/hive)

Multi-Agent Harness for Production AI.

**Language:** Python · **Author:** [aden-hive](https://github.com/aden-hive)

---

#### [open-multi-agent](https://github.com/JackChen-me/open-multi-agent)

![Stars](https://img.shields.io/github/stars/JackChen-me/open-multi-agent?style=social) ![Last commit](https://img.shields.io/github/last-commit/JackChen-me/open-multi-agent)

TypeScript multi-agent framework — one `runTeam()` call from goal to result. Auto task decomposition, parallel execution, three dependencies, deploys anywhere Node.js runs.

**Language:** TypeScript · **Author:** [JackChen-me](https://github.com/JackChen-me)

---

#### [ROMA](https://github.com/sentient-agi/ROMA)

![Stars](https://img.shields.io/github/stars/sentient-agi/ROMA?style=social) ![Last commit](https://img.shields.io/github/last-commit/sentient-agi/ROMA)

Recursive-Open-Meta-Agent — a meta-agent framework for building high-performance multi-agent systems.

---

#### [Shannon](https://github.com/Kocoro-lab/Shannon)

![Stars](https://img.shields.io/github/stars/Kocoro-lab/Shannon?style=social) ![Last commit](https://img.shields.io/github/last-commit/Kocoro-lab/Shannon)

A production-oriented multi-agent orchestration framework.

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

#### [gh-aw](https://github.com/github/gh-aw)

![Stars](https://img.shields.io/github/stars/github/gh-aw?style=social) ![Last commit](https://img.shields.io/github/last-commit/github/gh-aw)

GitHub Agentic Workflows — a `gh` extension for defining and running agentic workflows.

---

#### [oh-my-openagent](https://github.com/code-yeongyu/oh-my-openagent)

![Stars](https://img.shields.io/github/stars/code-yeongyu/oh-my-openagent?style=social) ![Last commit](https://img.shields.io/github/last-commit/code-yeongyu/oh-my-openagent)

omo — an agent harness (formerly oh-my-opencode).

---

#### [OpenAgentsControl](https://github.com/darrenhinde/OpenAgentsControl)

![Stars](https://img.shields.io/github/stars/darrenhinde/OpenAgentsControl?style=social) ![Last commit](https://img.shields.io/github/last-commit/darrenhinde/OpenAgentsControl)

Plan-first AI agent framework with approval-based execution, multi-language support, and built-in testing/review — built for OpenCode.

---

#### [openakita](https://github.com/openakita/openakita)

![Stars](https://img.shields.io/github/stars/openakita/openakita?style=social) ![Last commit](https://img.shields.io/github/last-commit/openakita/openakita)

Open-source AI assistant framework with skills and agent architecture.

**Language:** Python · **Author:** [openakita](https://github.com/openakita)

---

#### [OpenHarness](https://github.com/HKUDS/OpenHarness)

![Stars](https://img.shields.io/github/stars/HKUDS/OpenHarness?style=social) ![Last commit](https://img.shields.io/github/last-commit/HKUDS/OpenHarness)

Open Agent Harness — research project from HKUDS.

**Language:** Python · **Author:** [HKUDS](https://github.com/HKUDS)

---

#### [stakpak/agent](https://github.com/stakpak/agent)

![Stars](https://img.shields.io/github/stars/stakpak/agent?style=social) ![Last commit](https://img.shields.io/github/last-commit/stakpak/agent) ![UI](https://img.shields.io/badge/UI-CLI-green) ![Use](https://img.shields.io/badge/Use-Sysadmin-yellow)

Ship your code, on autopilot. An open source agent that lives on your machines 24/7 and keeps your apps running.

**Language:** Rust · **Author:** [stakpak](https://github.com/stakpak)

---

#### [statelyai/agent](https://github.com/statelyai/agent)

![Stars](https://img.shields.io/github/stars/statelyai/agent?style=social) ![Last commit](https://img.shields.io/github/last-commit/statelyai/agent)

Create state-machine-powered LLM agents using XState.

**Language:** TypeScript · **Author:** [statelyai](https://github.com/statelyai)

---

## 5. Computer-Use & Agent Operating Systems

Agents that drive the whole OS / desktop — mouse, keyboard, windows, filesystem — rather than being confined to a repo.

#### [agent-desktop](https://github.com/lahfir/agent-desktop)

![Stars](https://img.shields.io/github/stars/lahfir/agent-desktop?style=social) ![Last commit](https://img.shields.io/github/last-commit/lahfir/agent-desktop) ![UI](https://img.shields.io/badge/UI-CLI-green) ![Use](https://img.shields.io/badge/Use-Sysadmin-yellow)

Native desktop automation CLI for AI agents. Controls any app through OS accessibility trees with structured JSON output.

**Language:** Rust · **Author:** [lahfir](https://github.com/lahfir)

---

#### [Agent-S](https://github.com/simular-ai/Agent-S)

![Stars](https://img.shields.io/github/stars/simular-ai/Agent-S?style=social) ![Last commit](https://img.shields.io/github/last-commit/simular-ai/Agent-S) ![Use](https://img.shields.io/badge/Use-Sysadmin-yellow)

Open agentic framework that uses computers like a human.

**Language:** Python · **Author:** [simular-ai](https://github.com/simular-ai)

---

#### [AgentCPM-GUI](https://github.com/OpenBMB/AgentCPM-GUI)

![Stars](https://img.shields.io/github/stars/OpenBMB/AgentCPM-GUI?style=social) ![Last commit](https://img.shields.io/github/last-commit/OpenBMB/AgentCPM-GUI) ![Local](https://img.shields.io/badge/Local-Yes-orange)

On-device GUI agent for operating Android apps, with reinforcement fine-tuning for efficient task execution.

---

#### [clawdcursor](https://github.com/AmrDab/clawdcursor)

![Stars](https://img.shields.io/github/stars/AmrDab/clawdcursor?style=social) ![Last commit](https://img.shields.io/github/last-commit/AmrDab/clawdcursor) ![Use](https://img.shields.io/badge/Use-Sysadmin-yellow)

AI desktop agent that sees your screen, controls your cursor, and completes tasks autonomously.

**Language:** TypeScript · **Author:** [AmrDab](https://github.com/AmrDab)

---

#### [cua](https://github.com/trycua/cua)

![Stars](https://img.shields.io/github/stars/trycua/cua?style=social) ![Last commit](https://img.shields.io/github/last-commit/trycua/cua) ![Use](https://img.shields.io/badge/Use-Sysadmin-yellow)

Open-source infrastructure for computer-use agents — sandboxes, SDKs, and benchmarks for agents that control macOS/Linux/Windows desktops.

**Language:** Python · **Author:** [trycua](https://github.com/trycua)

---

#### [MobiAgent](https://github.com/IPADS-SAI/MobiAgent)

![Stars](https://img.shields.io/github/stars/IPADS-SAI/MobiAgent?style=social) ![Last commit](https://img.shields.io/github/last-commit/IPADS-SAI/MobiAgent)

An intelligent GUI agent for mobile phones.

---

#### [MobileAgent](https://github.com/X-PLUG/MobileAgent)

![Stars](https://img.shields.io/github/stars/X-PLUG/MobileAgent?style=social) ![Last commit](https://img.shields.io/github/last-commit/X-PLUG/MobileAgent) ![Use](https://img.shields.io/badge/Use-Sysadmin-yellow)

Mobile-Agent: a powerful GUI agent family for operating mobile devices.

**Language:** Python · **Author:** [X-PLUG](https://github.com/X-PLUG)

---

#### [open-computer-use](https://github.com/coasty-ai/open-computer-use)

![Stars](https://img.shields.io/github/stars/coasty-ai/open-computer-use?style=social) ![Last commit](https://img.shields.io/github/last-commit/coasty-ai/open-computer-use) ![Use](https://img.shields.io/badge/Use-Sysadmin-yellow)

State-of-the-art (82% OSWorld Verified) computer-using agent, fully open-source.

**Language:** TypeScript · **Author:** [coasty-ai](https://github.com/coasty-ai)

---

#### [openfang](https://github.com/RightNow-AI/openfang)

![Stars](https://img.shields.io/github/stars/RightNow-AI/openfang?style=social) ![Last commit](https://img.shields.io/github/last-commit/RightNow-AI/openfang) ![Use](https://img.shields.io/badge/Use-Sysadmin-yellow)

Open-source Agent Operating System.

**Language:** Rust · **Author:** [RightNow-AI](https://github.com/RightNow-AI)

---

#### [openyak](https://github.com/openyak/openyak)

![Stars](https://img.shields.io/github/stars/openyak/openyak?style=social) ![Last commit](https://img.shields.io/github/last-commit/openyak/openyak) ![Local](https://img.shields.io/badge/Local-Yes-orange) ![Use](https://img.shields.io/badge/Use-Sysadmin-yellow)

Open-source desktop AI agent that handles your documents, files, and daily workflows — locally, with any model.

**Language:** Python · **Author:** [openyak](https://github.com/openyak)

---

#### [OpenRoom](https://github.com/MiniMax-AI/OpenRoom)

![Stars](https://img.shields.io/github/stars/MiniMax-AI/OpenRoom?style=social) ![Last commit](https://img.shields.io/github/last-commit/MiniMax-AI/OpenRoom) ![Use](https://img.shields.io/badge/Use-Sysadmin-yellow)

Browser-based desktop where an AI agent operates every app through natural language.

**Language:** TypeScript · **Author:** [MiniMax-AI](https://github.com/MiniMax-AI)

---

#### [surf](https://github.com/e2b-dev/surf)

![Stars](https://img.shields.io/github/stars/e2b-dev/surf?style=social) ![Last commit](https://img.shields.io/github/last-commit/e2b-dev/surf) ![Use](https://img.shields.io/badge/Use-Sysadmin-yellow)

Computer-use AI agent powered by OpenAI that interacts with E2B's virtual desktop environment through natural language. Harness runs locally; the sandboxed desktop is E2B-hosted.

**Language:** TypeScript · **Author:** [e2b-dev](https://github.com/e2b-dev)

---

#### [terminaI](https://github.com/Prof-Harita/terminaI)

![Stars](https://img.shields.io/github/stars/Prof-Harita/terminaI?style=social) ![Last commit](https://img.shields.io/github/last-commit/Prof-Harita/terminaI) ![Use](https://img.shields.io/badge/Use-Sysadmin-yellow)

Local-first alternative to Cowork-style computer assistants: real PTY terminal ops, explicit approvals, JSONL audit logs. Windows + Linux + macOS, model-agnostic.

**Language:** TypeScript · **Author:** [Prof-Harita](https://github.com/Prof-Harita)

---

#### [UI-TARS-desktop](https://github.com/bytedance/UI-TARS-desktop)

![Stars](https://img.shields.io/github/stars/bytedance/UI-TARS-desktop?style=social) ![Last commit](https://img.shields.io/github/last-commit/bytedance/UI-TARS-desktop) ![UI](https://img.shields.io/badge/UI-GUI-green) ![Use](https://img.shields.io/badge/Use-Sysadmin-yellow)

Open-source multimodal AI agent stack connecting cutting-edge AI models and agent infra, by ByteDance.

**Language:** TypeScript · **Author:** [bytedance](https://github.com/bytedance)

---

## 6. Desktop GUIs & Cowork Clones

Desktop GUI applications for running agents, including the rapidly growing crop of open-source Claude Cowork alternatives.

#### [amon-agent](https://github.com/liruifengv/amon-agent)

![Stars](https://img.shields.io/github/stars/liruifengv/amon-agent?style=social) ![Last commit](https://img.shields.io/github/last-commit/liruifengv/amon-agent) ![UI](https://img.shields.io/badge/UI-GUI-green)

Amon — your AI coworker running on your desktop.

**Language:** TypeScript · **Author:** [liruifengv](https://github.com/liruifengv)

---

#### [ClawX](https://github.com/ValueCell-ai/ClawX)

![Stars](https://img.shields.io/github/stars/ValueCell-ai/ClawX?style=social) ![Last commit](https://img.shields.io/github/last-commit/ValueCell-ai/ClawX) ![UI](https://img.shields.io/badge/UI-GUI-green)

Desktop GUI for OpenClaw — turns CLI-based AI orchestration into a desktop experience.

**Language:** TypeScript · **Author:** [ValueCell-ai](https://github.com/ValueCell-ai)

---

#### [CodePilot](https://github.com/op7418/CodePilot)

![Stars](https://img.shields.io/github/stars/op7418/CodePilot?style=social) ![Last commit](https://img.shields.io/github/last-commit/op7418/CodePilot) ![UI](https://img.shields.io/badge/UI-GUI-green) ![MCP](https://img.shields.io/badge/MCP-Yes-purple)

Multi-model AI agent desktop client — connect any provider, extend with MCP & skills, control from your phone. Built with Electron + Next.js.

**Language:** TypeScript · **Author:** [op7418](https://github.com/op7418)

---

#### [CoWork-OS](https://github.com/CoWork-OS/CoWork-OS)

![Stars](https://img.shields.io/github/stars/CoWork-OS/CoWork-OS?style=social) ![Last commit](https://img.shields.io/github/last-commit/CoWork-OS/CoWork-OS) ![Local](https://img.shields.io/badge/Local-Yes-orange)

Self-hosted OS for personal AI agents. Security-first, multi-channel (WhatsApp, Telegram, Discord, Slack, iMessage), multi-provider (Claude, GPT, Gemini, Ollama).

**Language:** TypeScript · **Author:** [CoWork-OS](https://github.com/CoWork-OS)

---

#### [Deep Agents UI](https://github.com/langchain-ai/deep-agents-ui)

![Stars](https://img.shields.io/github/stars/langchain-ai/deep-agents-ui?style=social) ![Last commit](https://img.shields.io/github/last-commit/langchain-ai/deep-agents-ui) ![UI](https://img.shields.io/badge/UI-GUI-green)

Custom UI for LangChain's Deep Agents.

---

#### [Deepseek-Cowork](https://github.com/imjszhang/Deepseek-Cowork)

![Stars](https://img.shields.io/github/stars/imjszhang/Deepseek-Cowork?style=social) ![Last commit](https://img.shields.io/github/last-commit/imjszhang/Deepseek-Cowork) ![UI](https://img.shields.io/badge/UI-GUI-green)

Claude Cowork alternative — browser automation & AI assistant powered by DeepSeek.

**Language:** JavaScript · **Author:** [imjszhang](https://github.com/imjszhang)

---

#### [eigent](https://github.com/eigent-ai/eigent)

![Stars](https://img.shields.io/github/stars/eigent-ai/eigent?style=social) ![Last commit](https://img.shields.io/github/last-commit/eigent-ai/eigent) ![UI](https://img.shields.io/badge/UI-GUI-green) ![Local](https://img.shields.io/badge/Local-Yes-orange)

Open-source Cowork desktop. Local and free alternative to Claude Cowork.

**Language:** TypeScript · **Author:** [eigent-ai](https://github.com/eigent-ai)

---

#### [hello-halo](https://github.com/openkursar/hello-halo)

![Stars](https://img.shields.io/github/stars/openkursar/hello-halo?style=social) ![Last commit](https://img.shields.io/github/last-commit/openkursar/hello-halo) ![UI](https://img.shields.io/badge/UI-GUI-green)

7×24 desktop AI agent with visual interface, remote access, file management, and built-in AI browser.

**Language:** TypeScript · **Author:** [openkursar](https://github.com/openkursar)

---

#### [kuse_cowork](https://github.com/kuse-ai/kuse_cowork)

![Stars](https://img.shields.io/github/stars/kuse-ai/kuse_cowork?style=social) ![Last commit](https://img.shields.io/github/last-commit/kuse-ai/kuse_cowork) ![UI](https://img.shields.io/badge/UI-GUI-green)

Open-source alternative to Claude Cowork desktop app, by Kuse.

**Language:** Rust · **Author:** [kuse-ai](https://github.com/kuse-ai)

---

#### [lemonai](https://github.com/hexdocom/lemonai)

![Stars](https://img.shields.io/github/stars/hexdocom/lemonai?style=social) ![Last commit](https://img.shields.io/github/last-commit/hexdocom/lemonai) ![Local](https://img.shields.io/badge/Local-Yes-orange)

Full-stack open-source self-evolving general AI agent — a fully local alternative to platforms like Manus and Genspark.

**Language:** JavaScript · **Author:** [hexdocom](https://github.com/hexdocom)

---

#### [magic](https://github.com/polterguy/magic)

![Stars](https://img.shields.io/github/stars/polterguy/magic?style=social) ![Last commit](https://img.shields.io/github/last-commit/polterguy/magic) ![UI](https://img.shields.io/badge/UI-GUI-green) ![Use](https://img.shields.io/badge/Use-Code-yellow)

Fully autonomous AI-based software development assistant.

**Language:** C# · **Author:** [polterguy](https://github.com/polterguy)

---

#### [open-claude-cowork (Composio)](https://github.com/ComposioHQ/open-claude-cowork)

![Stars](https://img.shields.io/github/stars/ComposioHQ/open-claude-cowork?style=social) ![Last commit](https://img.shields.io/github/last-commit/ComposioHQ/open-claude-cowork) ![UI](https://img.shields.io/badge/UI-GUI-green)

Open-source Claude Cowork with 500+ SaaS app integrations.

**Language:** JavaScript · **Author:** [ComposioHQ](https://github.com/ComposioHQ)

---

#### [Open-Claude-Cowork (DevAgentForge)](https://github.com/DevAgentForge/Open-Claude-Cowork)

![Stars](https://img.shields.io/github/stars/DevAgentForge/Open-Claude-Cowork?style=social) ![Last commit](https://img.shields.io/github/last-commit/DevAgentForge/Open-Claude-Cowork) ![UI](https://img.shields.io/badge/UI-GUI-green)

Open-source Claude Cowork desktop AI assistant for programming, file management, and general tasks.

**Language:** TypeScript · **Author:** [DevAgentForge](https://github.com/DevAgentForge)

---

#### [OpenCowork (AIDotNet)](https://github.com/AIDotNet/OpenCowork)

![Stars](https://img.shields.io/github/stars/AIDotNet/OpenCowork?style=social) ![Last commit](https://img.shields.io/github/last-commit/AIDotNet/OpenCowork) ![UI](https://img.shields.io/badge/UI-GUI-green)

Open-source Claude Cowork for Windows, macOS, and Linux.

**Language:** TypeScript · **Author:** [AIDotNet](https://github.com/AIDotNet)

---

#### [openchamber](https://github.com/openchamber/openchamber)

![Stars](https://img.shields.io/github/stars/openchamber/openchamber?style=social) ![Last commit](https://img.shields.io/github/last-commit/openchamber/openchamber) ![UI](https://img.shields.io/badge/UI-GUI-green)

Desktop and web interface for the opencode AI agent.

**Language:** TypeScript · **Author:** [openchamber](https://github.com/openchamber)

---

#### [openwork](https://github.com/different-ai/openwork)

![Stars](https://img.shields.io/github/stars/different-ai/openwork?style=social) ![Last commit](https://img.shields.io/github/last-commit/different-ai/openwork) ![UI](https://img.shields.io/badge/UI-GUI-green)

Open-source alternative to Claude Cowork built for teams, powered by opencode.

**Language:** TypeScript · **Author:** [different-ai](https://github.com/different-ai)

---

#### [skales](https://github.com/skalesapp/skales)

![Stars](https://img.shields.io/github/stars/skalesapp/skales?style=social) ![Last commit](https://img.shields.io/github/last-commit/skalesapp/skales) ![UI](https://img.shields.io/badge/UI-GUI-green) ![Local](https://img.shields.io/badge/Local-Yes-orange)

Local desktop AI agent for Windows/macOS/Linux with Agent Skills (SKILL.md), autonomous coding, multi-agent teams, desktop automation, 15+ AI providers. No Docker, no terminal.

**Language:** TypeScript · **Author:** [skalesapp](https://github.com/skalesapp)

---

#### [witsy](https://github.com/nbonamy/witsy)

![Stars](https://img.shields.io/github/stars/nbonamy/witsy?style=social) ![Last commit](https://img.shields.io/github/last-commit/nbonamy/witsy) ![UI](https://img.shields.io/badge/UI-GUI-green) ![MCP](https://img.shields.io/badge/MCP-Yes-purple)

Desktop AI assistant / universal MCP client.

**Language:** TypeScript · **Author:** [nbonamy](https://github.com/nbonamy)

---

#### [workany](https://github.com/workany-ai/workany)

![Stars](https://img.shields.io/github/stars/workany-ai/workany?style=social) ![Last commit](https://img.shields.io/github/last-commit/workany-ai/workany) ![UI](https://img.shields.io/badge/UI-GUI-green)

Desktop agent for any task.

**Language:** TypeScript · **Author:** [workany-ai](https://github.com/workany-ai)

---

## 7. Personal AI Assistants

General-purpose, always-on personal assistants that run on your machine.

#### [clawlet](https://github.com/mosaxiv/clawlet)

![Stars](https://img.shields.io/github/stars/mosaxiv/clawlet?style=social) ![Last commit](https://img.shields.io/github/last-commit/mosaxiv/clawlet)

Ultra-lightweight, efficient personal AI assistant.

**Language:** Go · **Author:** [mosaxiv](https://github.com/mosaxiv)

---

#### [CoPaw](https://github.com/agentscope-ai/CoPaw)

![Stars](https://img.shields.io/github/stars/agentscope-ai/CoPaw?style=social) ![Last commit](https://img.shields.io/github/last-commit/agentscope-ai/CoPaw)

Personal AI assistant easy to install and deploy on your own machine. Supports multiple chat apps with extensible capabilities.

**Language:** Python · **Author:** [agentscope-ai](https://github.com/agentscope-ai)

---

#### [deepchat](https://github.com/ThinkInAIXYZ/deepchat)

![Stars](https://img.shields.io/github/stars/ThinkInAIXYZ/deepchat?style=social) ![Last commit](https://img.shields.io/github/last-commit/ThinkInAIXYZ/deepchat) ![UI](https://img.shields.io/badge/UI-GUI-green)

Smart assistant that connects powerful AI to your personal world.

**Language:** TypeScript · **Author:** [ThinkInAIXYZ](https://github.com/ThinkInAIXYZ)

---

#### [Everywhere](https://github.com/DearVa/Everywhere)

![Stars](https://img.shields.io/github/stars/DearVa/Everywhere?style=social) ![Last commit](https://img.shields.io/github/last-commit/DearVa/Everywhere) ![UI](https://img.shields.io/badge/UI-GUI-green) ![MCP](https://img.shields.io/badge/MCP-Yes-purple)

Context-aware AI desktop assistant that integrates multiple LLMs and MCP tools.

**Language:** C# · **Author:** [DearVa](https://github.com/DearVa)

---

#### [goclaw](https://github.com/smallnest/goclaw)

![Stars](https://img.shields.io/github/stars/smallnest/goclaw?style=social) ![Last commit](https://img.shields.io/github/last-commit/smallnest/goclaw)

Open-source AI assistant framework, a Go-flavored openclaw.

**Language:** Go · **Author:** [smallnest](https://github.com/smallnest)

---

#### [inbox-zero](https://github.com/elie222/inbox-zero)

![Stars](https://img.shields.io/github/stars/elie222/inbox-zero?style=social) ![Last commit](https://img.shields.io/github/last-commit/elie222/inbox-zero) ![UI](https://img.shields.io/badge/UI-GUI-green)

Open-source AI personal assistant for email — reach inbox zero fast. _Domain-specific: email._

**Language:** TypeScript · **Author:** [elie222](https://github.com/elie222)

---

#### [leon](https://github.com/leon-ai/leon)

![Stars](https://img.shields.io/github/stars/leon-ai/leon?style=social) ![Last commit](https://img.shields.io/github/last-commit/leon-ai/leon)

Leon — your open-source personal assistant.

**Language:** TypeScript · **Author:** [leon-ai](https://github.com/leon-ai)

---

#### [mimiclaw](https://github.com/memovai/mimiclaw)

![Stars](https://img.shields.io/github/stars/memovai/mimiclaw?style=social) ![Last commit](https://img.shields.io/github/last-commit/memovai/mimiclaw)

Run OpenClaw on a $5 chip — hardware-oriented agent OS with no Linux/Node/Raspberry Pi dependency.

**Language:** C · **Author:** [memovai](https://github.com/memovai)

---

#### [nullclaw](https://github.com/nullclaw/nullclaw)

![Stars](https://img.shields.io/github/stars/nullclaw/nullclaw?style=social) ![Last commit](https://img.shields.io/github/last-commit/nullclaw/nullclaw)

Fastest, smallest, fully autonomous AI assistant infrastructure, written in Zig.

**Language:** Zig · **Author:** [nullclaw](https://github.com/nullclaw)

---

#### [openclaw](https://github.com/openclaw/openclaw)

![Stars](https://img.shields.io/github/stars/openclaw/openclaw?style=social) ![Last commit](https://img.shields.io/github/last-commit/openclaw/openclaw)

Your own personal AI assistant — any OS, any platform. 🦞

**Language:** TypeScript · **Author:** [openclaw](https://github.com/openclaw)

---

#### [RoboClaw](https://github.com/MINT-SJTU/RoboClaw)

![Stars](https://img.shields.io/github/stars/MINT-SJTU/RoboClaw?style=social) ![Last commit](https://img.shields.io/github/last-commit/MINT-SJTU/RoboClaw)

Embodied AI assistant from MINT-SJTU. _Outlier: embodied/robotics — parked here pending a dedicated section._

**Language:** Python · **Author:** [MINT-SJTU](https://github.com/MINT-SJTU)

---

#### [Sentient](https://github.com/existence-master/Sentient)

![Stars](https://img.shields.io/github/stars/existence-master/Sentient?style=social) ![Last commit](https://img.shields.io/github/last-commit/existence-master/Sentient)

A personal AI assistant for everyone.

**Language:** Python · **Author:** [existence-master](https://github.com/existence-master)

---

#### [youclaw](https://github.com/CodePhiliaX/youclaw)

![Stars](https://img.shields.io/github/stars/CodePhiliaX/youclaw?style=social) ![Last commit](https://img.shields.io/github/last-commit/CodePhiliaX/youclaw)

🦞 Personal AI assistant with memory, skills, and scheduled tasks.

**Language:** TypeScript · **Author:** [CodePhiliaX](https://github.com/CodePhiliaX)

---

#### [zeroclaw](https://github.com/zeroclaw-labs/zeroclaw)

![Stars](https://img.shields.io/github/stars/zeroclaw-labs/zeroclaw?style=social) ![Last commit](https://img.shields.io/github/last-commit/zeroclaw-labs/zeroclaw)

Fast, small, fully autonomous AI personal-assistant infrastructure — any OS, any platform.

**Language:** Rust · **Author:** [zeroclaw-labs](https://github.com/zeroclaw-labs)

---

## 8. Terminal Assistants

Shell-integrated AI helpers — less "agent in a repo", more "AI that lives in your terminal".

#### [aichat](https://github.com/sigoden/aichat)

![Stars](https://img.shields.io/github/stars/sigoden/aichat?style=social) ![Last commit](https://img.shields.io/github/last-commit/sigoden/aichat) ![UI](https://img.shields.io/badge/UI-CLI-green) ![Local](https://img.shields.io/badge/Local-Yes-orange)

All-in-one LLM CLI with Shell Assistant, Chat-REPL, RAG, and AI tools/agents. Supports OpenAI, Claude, Gemini, Ollama, Groq, and more.

**Language:** Rust · **Author:** [sigoden](https://github.com/sigoden)

---

#### [shell-ai](https://github.com/ibigio/shell-ai)

![Stars](https://img.shields.io/github/stars/ibigio/shell-ai?style=social) ![Last commit](https://img.shields.io/github/last-commit/ibigio/shell-ai) ![UI](https://img.shields.io/badge/UI-CLI-green)

A delightfully minimal, remarkably powerful AI shell assistant.

**Language:** Go · **Author:** [ibigio](https://github.com/ibigio)

---

#### [tmuxai](https://github.com/alvinunreal/tmuxai)

![Stars](https://img.shields.io/github/stars/alvinunreal/tmuxai?style=social) ![Last commit](https://img.shields.io/github/last-commit/alvinunreal/tmuxai) ![UI](https://img.shields.io/badge/UI-TUI-green)

AI-powered, non-intrusive terminal assistant that lives inside tmux.

**Language:** Go · **Author:** [alvinunreal](https://github.com/alvinunreal)

---

## 9. Protocols

Open protocols and specifications for desktop agent interop.

#### [ag-ui](https://github.com/ag-ui-protocol/ag-ui)

![Stars](https://img.shields.io/github/stars/ag-ui-protocol/ag-ui?style=social) ![Last commit](https://img.shields.io/github/last-commit/ag-ui-protocol/ag-ui)

AG-UI — the Agent-User Interaction Protocol. Bring agents into frontend applications.

**Language:** Python · **Author:** [ag-ui-protocol](https://github.com/ag-ui-protocol)

---

## 10. Wallets & Payments

Capabilities for on-device agents that need to hold funds or transact.

#### [agentkit](https://github.com/coinbase/agentkit)

![Stars](https://img.shields.io/github/stars/coinbase/agentkit?style=social) ![Last commit](https://img.shields.io/github/last-commit/coinbase/agentkit)

"Every AI agent deserves a wallet." Coinbase's toolkit for giving agents on-chain wallet capabilities.

**Language:** TypeScript · **Author:** [coinbase](https://github.com/coinbase)

---

#### [AgentKit (0xGasless)](https://github.com/0xgasless/agentkit)

![Stars](https://img.shields.io/github/stars/0xgasless/agentkit?style=social) ![Last commit](https://img.shields.io/github/last-commit/0xgasless/agentkit)

Toolkit giving AI agents access to crypto wallets and on-chain functionality, powered by the 0xGasless SDK.

---

#### [GOAT](https://github.com/goat-sdk/goat)

![Stars](https://img.shields.io/github/stars/goat-sdk/goat?style=social) ![Last commit](https://img.shields.io/github/last-commit/goat-sdk/goat)

The leading agentic finance toolkit for AI agents.

---

## 11. Skill Collections

Collections of portable agent "skills" — prompt/instruction packages designed to plug into multiple agent harnesses.

#### [addyosmani/agent-skills](https://github.com/addyosmani/agent-skills)

![Stars](https://img.shields.io/github/stars/addyosmani/agent-skills?style=social) ![Last commit](https://img.shields.io/github/last-commit/addyosmani/agent-skills)

Production-grade engineering skills for AI coding agents.

**Language:** Shell · **Author:** [addyosmani](https://github.com/addyosmani)

---

#### [Agent-Skills-for-Context-Engineering](https://github.com/muratcankoylan/Agent-Skills-for-Context-Engineering)

![Stars](https://img.shields.io/github/stars/muratcankoylan/Agent-Skills-for-Context-Engineering?style=social) ![Last commit](https://img.shields.io/github/last-commit/muratcankoylan/Agent-Skills-for-Context-Engineering)

Collection of Agent Skills for context engineering, multi-agent architectures, and production agent systems.

**Language:** Python · **Author:** [muratcankoylan](https://github.com/muratcankoylan)

---

#### [awesome-agent-skills](https://github.com/VoltAgent/awesome-agent-skills)

![Stars](https://img.shields.io/github/stars/VoltAgent/awesome-agent-skills?style=social) ![Last commit](https://img.shields.io/github/last-commit/VoltAgent/awesome-agent-skills)

Claude Code Skills and 1000+ agent skills from official dev teams and the community — compatible with Codex, Antigravity, Gemini CLI, Cursor, and others.

**Author:** [VoltAgent](https://github.com/VoltAgent)

---

#### [superpowers](https://github.com/obra/superpowers)

![Stars](https://img.shields.io/github/stars/obra/superpowers?style=social) ![Last commit](https://img.shields.io/github/last-commit/obra/superpowers)

An agentic skills framework and software development methodology that works.

**Language:** Shell · **Author:** [obra](https://github.com/obra)

---

#### [vercel-labs/agent-skills](https://github.com/vercel-labs/agent-skills)

![Stars](https://img.shields.io/github/stars/vercel-labs/agent-skills?style=social) ![Last commit](https://img.shields.io/github/last-commit/vercel-labs/agent-skills)

Vercel's official collection of agent skills.

**Language:** JavaScript · **Author:** [vercel-labs](https://github.com/vercel-labs)

---

#### [apify/agent-skills](https://github.com/apify/agent-skills)

![Stars](https://img.shields.io/github/stars/apify/agent-skills?style=social) ![Last commit](https://img.shields.io/github/last-commit/apify/agent-skills)

Collection of Apify Agent Skills for web scraping and automation.

---

#### [aws-agent-skills](https://github.com/itsmostafa/aws-agent-skills)

![Stars](https://img.shields.io/github/stars/itsmostafa/aws-agent-skills?style=social) ![Last commit](https://img.shields.io/github/last-commit/itsmostafa/aws-agent-skills)

AWS skills for agents.

---

#### [awesome-agent-skills (libukai)](https://github.com/libukai/awesome-agent-skills)

![Stars](https://img.shields.io/github/stars/libukai/awesome-agent-skills?style=social) ![Last commit](https://img.shields.io/github/last-commit/libukai/awesome-agent-skills)

The Ultimate Guide to Agent Skills: quickstart, resources, features, and toolkit.

---

#### [obsidian-skills](https://github.com/kepano/obsidian-skills)

![Stars](https://img.shields.io/github/stars/kepano/obsidian-skills?style=social) ![Last commit](https://img.shields.io/github/last-commit/kepano/obsidian-skills)

Agent skills for Obsidian — teach your agent to use Markdown, Bases, JSON Canvas, and the Obsidian CLI.

---

#### [tech-leads-club/agent-skills](https://github.com/tech-leads-club/agent-skills)

![Stars](https://img.shields.io/github/stars/tech-leads-club/agent-skills?style=social) ![Last commit](https://img.shields.io/github/last-commit/tech-leads-club/agent-skills)

Secure, validated skill registry for professional AI coding agents — extends Claude Code, Cursor, Copilot, Antigravity, and more.

---

## 12. Voice & Speech Agents

Agents whose primary interaction modality is voice — speech-to-speech, voice companions, realtime voice agents.

#### [livekit/agents](https://github.com/livekit/agents)

![Stars](https://img.shields.io/github/stars/livekit/agents?style=social) ![Last commit](https://img.shields.io/github/last-commit/livekit/agents)

Framework for building realtime voice AI agents.

**Language:** Python · **Author:** [livekit](https://github.com/livekit)

---

#### [my-neuro](https://github.com/morettt/my-neuro)

![Stars](https://img.shields.io/github/stars/morettt/my-neuro?style=social) ![Last commit](https://img.shields.io/github/last-commit/morettt/my-neuro) ![Local](https://img.shields.io/badge/Local-Yes-orange)

Create your own AI desktop companion with customizable characters and voice conversations (~1s response). Long-term memory, visual recognition, voice cloning, Live2D.

**Language:** Python · **Author:** [morettt](https://github.com/morettt)

---

#### [speech-to-speech](https://github.com/huggingface/speech-to-speech)

![Stars](https://img.shields.io/github/stars/huggingface/speech-to-speech?style=social) ![Last commit](https://img.shields.io/github/last-commit/huggingface/speech-to-speech) ![Local](https://img.shields.io/badge/Local-Yes-orange)

Build local voice agents with open-source models.

**Language:** Python · **Author:** [huggingface](https://github.com/huggingface)

---

## 13. Remote Access & Mobile UIs

Bridges that let you drive a desktop agent from your phone, tablet, or another device — keeping the agent loop on your machine.

#### [clsh](https://github.com/my-claude-utils/clsh)

![Stars](https://img.shields.io/github/stars/my-claude-utils/clsh?style=social) ![Last commit](https://img.shields.io/github/last-commit/my-claude-utils/clsh)

Access your terminal and your AI agent from any device — phone, tablet, desktop.

**Language:** TypeScript · **Author:** [my-claude-utils](https://github.com/my-claude-utils)

---

#### [opencode-manager](https://github.com/chriswritescode-dev/opencode-manager)

![Stars](https://img.shields.io/github/stars/chriswritescode-dev/opencode-manager?style=social) ![Last commit](https://img.shields.io/github/last-commit/chriswritescode-dev/opencode-manager) ![UI](https://img.shields.io/badge/UI-GUI-green)

Mobile-first web interface for opencode AI agents. Manage and code with multiple opencode agents from any device (phone, tablet, desktop). Git integration, file management, real-time chat, Docker deploy.

**Language:** TypeScript · **Author:** [chriswritescode-dev](https://github.com/chriswritescode-dev)

---

#### [paseo](https://github.com/getpaseo/paseo)

![Stars](https://img.shields.io/github/stars/getpaseo/paseo?style=social) ![Last commit](https://img.shields.io/github/last-commit/getpaseo/paseo)

Manage agents remotely from your phone, desktop, and CLI.

**Language:** TypeScript · **Author:** [getpaseo](https://github.com/getpaseo)

---

## 14. Memory

Memory layers that give on-device agents persistent recall across sessions.

#### [Beads](https://github.com/gastownhall/beads)

![Stars](https://img.shields.io/github/stars/gastownhall/beads?style=social) ![Last commit](https://img.shields.io/github/last-commit/gastownhall/beads)

A memory upgrade for your coding agent.

---

#### [Hindsight](https://github.com/vectorize-io/hindsight)

![Stars](https://img.shields.io/github/stars/vectorize-io/hindsight?style=social) ![Last commit](https://img.shields.io/github/last-commit/vectorize-io/hindsight)

Agent memory that learns over time.

---

#### [mem0](https://github.com/mem0ai/mem0)

![Stars](https://img.shields.io/github/stars/mem0ai/mem0?style=social) ![Last commit](https://img.shields.io/github/last-commit/mem0ai/mem0)

Universal memory layer for AI agents.

**Language:** Python · **Author:** [mem0ai](https://github.com/mem0ai)

---

## 15. Gateways & Proxies

Proxies and aggregators that sit between desktop agents and the services/tools they call.

#### [1mcp](https://github.com/1mcp-app/agent)

![Stars](https://img.shields.io/github/stars/1mcp-app/agent?style=social) ![Last commit](https://img.shields.io/github/last-commit/1mcp-app/agent) ![MCP](https://img.shields.io/badge/MCP-Yes-purple)

Unified MCP server that aggregates multiple MCP servers into one.

**Language:** TypeScript · **Author:** [1mcp-app](https://github.com/1mcp-app)

---

#### [agentgateway](https://github.com/agentgateway/agentgateway)

![Stars](https://img.shields.io/github/stars/agentgateway/agentgateway?style=social) ![Last commit](https://img.shields.io/github/last-commit/agentgateway/agentgateway) ![MCP](https://img.shields.io/badge/MCP-Yes-purple)

Next-generation agentic proxy for AI agents and MCP servers.

**Language:** Rust · **Author:** [agentgateway](https://github.com/agentgateway)

---

## 16. Browser Extensions & Web Agents

Browser-resident agents and toolkits for driving the browser from an on-device agent.

#### [AgentQL](https://github.com/tinyfish-io/agentql)

![Stars](https://img.shields.io/github/stars/tinyfish-io/agentql?style=social) ![Last commit](https://img.shields.io/github/last-commit/tinyfish-io/agentql)

Suite of tools for connecting AI to the web — query language and Playwright integrations for precise element interaction and data extraction.

---

#### [AIPex](https://github.com/AIPexStudio/AIPex)

![Stars](https://img.shields.io/github/stars/AIPexStudio/AIPex?style=social) ![Last commit](https://img.shields.io/github/last-commit/AIPexStudio/AIPex)

AI browser-automation assistant, privacy-first. Alternative to Manus Browser Operator, Claude Chrome, and Agent Browser.

**Language:** TypeScript · **Author:** [AIPexStudio](https://github.com/AIPexStudio)

---

#### [NativeMindExtension](https://github.com/NativeMindBrowser/NativeMindExtension)

![Stars](https://img.shields.io/github/stars/NativeMindBrowser/NativeMindExtension?style=social) ![Last commit](https://img.shields.io/github/last-commit/NativeMindBrowser/NativeMindExtension) ![Local](https://img.shields.io/badge/Local-Yes-orange)

NativeMind — fully private, open-source, on-device AI assistant that lives as a browser extension.

**Language:** TypeScript · **Author:** [NativeMindBrowser](https://github.com/NativeMindBrowser)

---

#### [Browser Agent (Magnitude)](https://github.com/magnitudedev/browser-agent)

![Stars](https://img.shields.io/github/stars/magnitudedev/browser-agent?style=social) ![Last commit](https://img.shields.io/github/last-commit/magnitudedev/browser-agent)

Open-source, vision-first browser agent.

---

#### [openbrowser](https://github.com/ntegrals/openbrowser)

![Stars](https://img.shields.io/github/stars/ntegrals/openbrowser?style=social) ![Last commit](https://img.shields.io/github/last-commit/ntegrals/openbrowser)

Autonomous toolkit that lets AI agents browse the web.

---

## 17. Research Assistants

Agents focused on long-form research, deep diligence, and report generation.

#### [Company Research Agent](https://github.com/guy-hartstein/company-research-agent)

![Stars](https://img.shields.io/github/stars/guy-hartstein/company-research-agent?style=social) ![Last commit](https://img.shields.io/github/last-commit/guy-hartstein/company-research-agent)

Multi-agent company-research / due-diligence tool built on LangGraph and Tavily, using Gemini and GPT-class models on the backend.

---

#### [Dexter](https://github.com/virattt/dexter)

![Stars](https://img.shields.io/github/stars/virattt/dexter?style=social) ![Last commit](https://img.shields.io/github/last-commit/virattt/dexter)

An autonomous agent for deep financial research.

---

## Related Resource Lists

Other curated lists worth browsing alongside this one.

#### [Awesome-AI](https://github.com/re50urces/Awesome-AI)

![Stars](https://img.shields.io/github/stars/re50urces/Awesome-AI?style=social) ![Last commit](https://img.shields.io/github/last-commit/re50urces/Awesome-AI)

Curated list of awesome AI tools — broader in scope than this list.

**Author:** [re50urces](https://github.com/re50urces)

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
