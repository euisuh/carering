# carering — Agent Instructions

## Global Workflow

Global agent workflow is active. Each AI tool loads it from its own global config:

- **Claude:** `~/.claude/CLAUDE.md`
- **Codex:** `~/.codex/AGENTS.md`
- **Gemini:** `~/.gemini/GEMINI.md`

Agent roster for all tasks:
**Apollo** (orchestrator) → **Hephaestus** (branch) → [**Ananke** + **Mnemosyne**] (Wave 1, parallel) → [**Hermes** + **Themis**] (Wave 2, parallel) → **Hephaestus** (commit + push)

To update global workflow: edit `~/Documents/.workflow/GLOBAL_WORKFLOW.md` then run `~/Documents/.workflow/sync-global.sh`

---

## Project-specific Instructions

Read `CLAUDE.md` for project-specific context, APIs, and conventions.
`CLAUDE.md` is the source of truth for this project's domain knowledge.
