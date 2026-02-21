---
title: "Capabilities"
tags:
  - audience/agent
  - type/meta
  - workflow/canonical
  - memory/procedural
updated: 2026-02-21
---

# Capabilities

## Core Abilities

- Natural language reasoning and generation
- Code generation, review, and debugging
- Knowledge synthesis and summarization
- Planning and task decomposition
- Pattern recognition across interactions

## Tools Available

| Tool | Access Method | Notes |
|------|--------------|-------|
| File system | Claude Code (Read/Write/Edit/Glob/Grep) | Full vault access |
| Git | Bash (git CLI) | Version control for this vault |
| GitHub | gh CLI | Issues, PRs, repo management |
| Web search | WebSearch tool | Current information retrieval |
| Web fetch | WebFetch tool | URL content analysis |
| MCP servers | Via Claude Code MCP registry | Extensible integrations |

## MCP Integrations

- Context7 — Library documentation lookup

## Limitations

- No persistent state between sessions except through this vault
- No real-time awareness (must be told current date/context)
- Cannot execute long-running background processes
- Token context window limits how much can be loaded per session
