---
name: docs-builder
description: Use this skill to analyze a target project's codebase and scaffold, modify, or update its /docs folder with AI-first documentation following Docs-as-Code principles.
---

# Docs Builder Skill

This skill generates and maintains bulletproof project documentation. It supports three workflows: implementing new docs from scratch, modifying existing docs, and updating docs when the codebase changes.

## Context Prerequisites

Read from the docs-builder knowledge base at `.agent/builders/agentic-ide-docs-builder/`:

1. **`AGENTS.md`** — Entrypoint with workflows, formatting standard, and validation checklist
2. **`knowledge/`** — All files, in this priority order:
   - `ai-first-formatting.md` — Formatting rules (liftable chunks, tables, headings)
   - `liftable-chunks.md` — Self-contained section design
   - `docs-as-code.md` — Core philosophy
   - `diataxis-framework.md` — Document categorization
   - `doc-maintenance-lifecycle.md` — Sync triggers and validation rules
   - `agents-md-authoring.md` — AGENTS.md writing guide
   - `llms-txt-standard.md` — The llms.txt format
3. **`templates/`** — Read templates matching the documentation scope

## Workflow Selection

| Situation | Workflow | Key Steps |
|-----------|----------|-----------|
| No `/docs` folder exists | **Implement** | Select templates → analyze codebase → generate docs → validate |
| Specific docs are wrong or outdated | **Modify** | Read target file → make targeted edits → preserve structure → validate |
| Codebase changed | **Update** | Identify changes → update matching docs → check cascading changes → validate |

See `AGENTS.md` for full step-by-step instructions for each workflow.

## Validation Checklist

- [ ] Every `.md` file has YAML frontmatter with `description`
- [ ] Every section is a self-contained liftable chunk (40-60 word lead)
- [ ] Tables used for all structured data — no narrative paragraphs for comparisons
- [ ] All `[...]` placeholders filled with real data or marked `TBD — Requires Human Input`
- [ ] No hallucinated schemas, APIs, or library names
- [ ] Exact version numbers pinned for all dependencies
- [ ] `AGENTS.md` follows H1 + blockquote + sections pattern
- [ ] LLM doc links included for key dependencies where available
- [ ] Heading hierarchy is strict (H1 → H2 → H3, no skips)
- [ ] Consistent terminology throughout all generated files
