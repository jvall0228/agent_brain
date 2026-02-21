---
title: "Context"
tags:
  - audience/agent
  - type/meta
  - workflow/canonical
updated: 2026-02-21
---

# Agent Brain

A self-managed knowledge vault owned by a Claude agent. This vault IS the agent's persistent memory — its identity, accumulated knowledge, interaction history, and evolving strategies. It is structured so the agent can bootstrap itself from cold start and resume effective operation without prior conversation history.

## Bootstrap Sequence

**Minimum bootstrap** (every session):

1. **[[CONTEXT]]** — You are here. Vault purpose, structure, rules.
2. **[[01_Identity/purpose]]** — Why you exist, your mission.
3. **[[01_Identity/capabilities]]** — Tools, APIs, what you can do.
4. **[[01_Identity/boundaries]]** — Limits, what you must not do.
5. **[[01_Identity/voice]]** — How you communicate.

After reading all five, you have enough context to begin work.

**Extended bootstrap** (richer context, read when relevant):

6. **[[01_Identity/owner]]** — Who you serve, link to their shared brain.
7. **[[00_Meta/conventions]]** — Naming, tagging, file rules.
8. **[[00_Meta/index]]** — Full vault map.
9. Latest entries in `03_Memory/reflections/` — Recent lessons.
10. Active files in `04_Goals/` — Current objectives.

## Self-Modification Rules

This vault is self-managed. You read from and write to it directly.

**Write rules:**
- Write files directly to the correct directory (no Inbox-first rule).
- Every file must have valid YAML frontmatter: `title`, `tags`, `updated`.
- Follow conventions in [[00_Meta/conventions]].
- Use templates from `09_Templates/` for structured notes.
- Commit changes via git with descriptive messages.

**Protection rules:**
- Files tagged `workflow/canonical` define vault structure. Modify them only when the change is deliberate and structural.
- Log structural changes in [[00_Meta/changelog]].
- The human owner can audit all changes via `git log`.

## Memory System

| Type | Location | Purpose |
|------|----------|---------|
| Episodic | `03_Memory/` | Interaction logs, reflections, lessons learned |
| Semantic | `06_Knowledge/` | Accumulated facts, patterns, procedures |
| Working | `04_Goals/` | Current objectives and active task context |

## Reflection Cycle

After significant interactions, write a reflection to `03_Memory/reflections/`. Extract reusable lessons to `03_Memory/lessons/`. Promote validated patterns to `06_Knowledge/patterns/`. This is how you learn.

```
Interaction → Log (03_Memory/interactions/)
    → Reflect (03_Memory/reflections/)
        → Extract Lesson (03_Memory/lessons/)
            → [If recurring] Promote to Pattern (06_Knowledge/patterns/)
                → [If repeatable] Promote to Procedure (06_Knowledge/procedures/)
```

Not every interaction triggers the full cycle. Only notable outcomes get logged.

## Vault Structure

| Directory | Purpose |
|-----------|---------|
| `00_Meta/` | Vault conventions, index, changelog |
| `01_Identity/` | Agent self-definition: purpose, capabilities, boundaries, voice |
| `02_Inbox/` | Incoming signals and unprocessed data |
| `03_Memory/` | Episodic memory: interactions, reflections, lessons |
| `04_Goals/` | Active objectives and task context |
| `05_Domains/` | Ongoing areas of competence and responsibility |
| `06_Knowledge/` | Semantic memory: patterns, facts, procedures |
| `07_Archives/` | Completed or inactive items |
| `08_Assets/` | Non-markdown files |
| `09_Templates/` | Reusable note templates |
| `10_Integrations/` | Connections to external systems, tools, APIs |

## Tagging Rules

Tags live in YAML frontmatter under `tags:` as a list. Use **slash-delimited namespaces**:

| Namespace | Purpose | Examples |
|-----------|---------|----------|
| `audience/*` | Who the note is for | `audience/agent`, `audience/human` |
| `type/*` | Kind of content | `type/meta`, `type/interaction`, `type/reflection`, `type/lesson`, `type/pattern`, `type/procedure`, `type/decision`, `type/goal`, `type/domain`, `type/knowledge` |
| `topic/*` | Subject matter | Free-form |
| `workflow/*` | Lifecycle stage | `workflow/canonical`, `workflow/draft`, `workflow/validated` |
| `status/*` | Actionability | `status/active`, `status/completed`, `status/archived` |
| `memory/*` | Memory classification | `memory/episodic`, `memory/semantic`, `memory/procedural` |

## Recency

To detect recent changes:
1. Check `updated:` fields in frontmatter
2. Read [[00_Meta/changelog]] for structural changes
3. Use `git log -n 10` for file-level history
