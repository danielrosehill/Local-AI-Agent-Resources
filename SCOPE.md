# Scope

This document defines what belongs in the Desktop-AI-Agents list and what doesn't. It's the source of truth for inclusion decisions — if something is ambiguous, this file should settle it (and if it can't, the file should be updated).

## Unifying principle

**The agent loop runs on the user's device.**

The underlying *model* may be hosted (Anthropic, OpenAI, xAI, Mistral, Moonshot, GitHub Copilot…) or fully local (Ollama, llama.cpp, vLLM). What matters is that the **harness** — the thing that plans, calls tools, reads the filesystem, shells out, keeps state — lives on the user's desktop, laptop, or workstation.

## In scope

- **CLI / TUI coding agents** you run inside a repo (aider, opencode, goose, OpenHands, copilot-cli, codex, kimi-cli, mistral-vibe, grok-cli…)
- **Sysadmin-style agents** that fluidly use the filesystem, shell, and networked resources (local or LAN) rather than being constrained to a repo
- **Tooling that wraps, manages, or orchestrates** on-device agent CLIs (session managers, task managers, parallel orchestrators)
- **MCP servers and tool providers** that plug into desktop agents
- **Multi-agent frameworks** whose orchestration runs locally
- **Agent operating systems / computer-use agents** that drive the host OS
- **Protocols and specifications** for desktop agent interop (AGENTS.md, Agent Skills, AG-UI, MCP-adjacent specs)
- **Harnesses and frameworks** for building desktop agents
- **Desktop-facing capabilities** like wallets, payments, browser automation that are designed to be embedded in an on-device agent

Vendor (first-party) and third-party projects are both in scope and are tagged separately.

## Out of scope

- **Server-deployed / cloud-hosted agent platforms.** If the agent loop runs in someone else's cloud, it's out — even if there's a thin CLI that talks to it.
- **Hosted SaaS agents** with no meaningful local execution.
- **IDE-first tools** where the CLI is only a companion to an IDE extension (Cursor, Cline-as-VSCode-extension, Continue…). If the CLI is a first-class way to run the agent, it's in.
- **Pure inference engines without an agent loop.** Ollama, llama.cpp, vLLM, LM Studio (as a server) are model runners, not agent runners. They're *used by* things in this list, but they're not themselves in scope.
- **Frameworks that don't support tool use or MCP directly.** A wrapper that only does chat completion isn't an agent harness.
- **Generic LLM client apps** (chat UIs, prompt playgrounds) without tool execution.
- **Agent-builder SDKs that only target cloud deployment** (LangGraph Cloud, hosted CrewAI deployments, etc.) — the SDK itself may be fine if it's commonly run on desktop, but cloud-first framings are out.

## Grey areas

These get judged case by case. If you're adding one, flag it in the PR description:

- **IDE extensions with a usable CLI mode.** Included if the CLI is first-class, excluded if it's a token-passing companion.
- **Computer-use agents** (Agent-S, UI-TARS, openfang). Included — they're the most "desktop-native" category there is — but they get their own section.
- **Multi-agent frameworks that can run either locally or in the cloud.** Included if the local mode is real and documented.
- **Browser automation tools.** Included only if they're explicitly designed to be driven by an on-device agent (not general Playwright/Puppeteer wrappers).
- **Vendor CLIs that are thin clients to a hosted backend.** Included if they do meaningful local tool execution; excluded if they're just a shell over a chat endpoint.

## What the badges mean

See the [badge legend in the README](./README.md#badge-legend). The badges are descriptive, not gatekeeping — an entry can be in scope without having every badge filled in. When in doubt, leave a badge off rather than guess.

## Updating this document

If you're unsure whether something belongs and this file doesn't answer the question, open an issue or PR to extend the grey-areas section. The goal is that the list stays coherent over time, not that it stays frozen.
