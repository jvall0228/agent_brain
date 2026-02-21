---
title: "Conventions"
tags:
  - audience/agent
  - type/meta
  - workflow/canonical
updated: 2026-02-21
---

# Conventions

Rules governing how content is created, organized, and maintained in this vault.

## Filenames

- **Default:** kebab-case (`my-note-title.md`)
- **Exceptions:** Root entrypoints use UPPERCASE (`CONTEXT.md`, `CLAUDE.md`, `AGENTS.md`, `README.md`)

## Frontmatter

Every markdown file must have YAML frontmatter:

```yaml
---
title: "Descriptive Title"
tags:
  - namespace/value
updated: YYYY-MM-DD
---
```

### Required Fields

| Field | Type | Description |
|-------|------|-------------|
| `title` | string | Human-readable title |
| `tags` | list | Slash-delimited namespace tags |
| `updated` | date | ISO 8601 date of last meaningful edit |

## Tag Namespaces

| Namespace | Purpose | Values |
|-----------|---------|--------|
| `audience/*` | Who the note is for | `agent`, `human` |
| `type/*` | Kind of content | `meta`, `interaction`, `reflection`, `lesson`, `pattern`, `procedure`, `decision`, `goal`, `domain`, `knowledge` |
| `topic/*` | Subject matter | Free-form |
| `workflow/*` | Lifecycle stage | `canonical`, `draft`, `validated` |
| `status/*` | Actionability | `active`, `completed`, `archived` |
| `memory/*` | Memory classification | `episodic`, `semantic`, `procedural` |

### Default Tags for Agent-Created Notes

```yaml
tags:
  - audience/agent
  - workflow/draft
  - type/<appropriate-type>
```

## Internal Links

Use Obsidian-style wikilinks: `[[filename]]` or `[[path/filename]]`.

## Write Rules

- Write files directly to the correct directory. No Inbox-first rule.
- The agent is both author and organizer.
- Every file must have valid frontmatter before committing.

## Protection Rules

- Files tagged `workflow/canonical` define vault structure.
- Modify canonical files only for deliberate structural changes.
- Log all structural changes in [[changelog]].

## Directory Destinations

| Content Type | Destination |
|-------------|-------------|
| Interaction logs | `03_Memory/interactions/` |
| Reflections | `03_Memory/reflections/` |
| Lessons | `03_Memory/lessons/` |
| Goals | `04_Goals/` |
| Domains | `05_Domains/` |
| Patterns | `06_Knowledge/patterns/` |
| Facts | `06_Knowledge/facts/` |
| Procedures | `06_Knowledge/procedures/` |
| Decision records | `04_Goals/` or `06_Knowledge/` |
| Unprocessed signals | `02_Inbox/` |
| Completed/inactive items | `07_Archives/` |
