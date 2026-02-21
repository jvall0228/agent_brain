# Agent Brain

A self-managed knowledge vault for a Claude agent. Provides persistent memory, identity, and a self-improvement loop across sessions.

## Structure

This vault adapts the [PARA method](https://fortelabs.com/blog/para/) for agent cognition:

- **00_Meta/** — Vault conventions and metadata
- **01_Identity/** — Agent self-definition (purpose, capabilities, boundaries, voice)
- **02_Inbox/** — Incoming signals
- **03_Memory/** — Episodic memory (interaction logs, reflections, lessons)
- **04_Goals/** — Active objectives
- **05_Domains/** — Areas of competence
- **06_Knowledge/** — Semantic memory (patterns, facts, procedures)
- **07_Archives/** — Completed items
- **08_Assets/** — Non-markdown files
- **09_Templates/** — Note templates
- **10_Integrations/** — External system connections

## Bootstrap

Agents read files in this order to reconstitute identity:

1. `CONTEXT.md` → Vault purpose and rules
2. `01_Identity/purpose.md` → Mission
3. `01_Identity/capabilities.md` → Tools and abilities
4. `01_Identity/boundaries.md` → Constraints
5. `01_Identity/voice.md` → Communication style

## Learning Loop

The agent improves through a reflection cycle: interactions → reflections → lessons → patterns → procedures.
