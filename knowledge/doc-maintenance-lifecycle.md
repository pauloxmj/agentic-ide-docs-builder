---
description: Full documentation lifecycle — creation, synchronization, validation, and deprecation — with AI-specific maintenance rules.
category: knowledge
---

# Documentation Maintenance Lifecycle

Documentation is a living system that must evolve with the codebase. The #1 risk in AI-assisted development is **state drift** — when AI writes code that invalidates docs, causing hallucinations in future sessions. This file defines the full lifecycle for preventing drift.

## The Four Phases

### Phase 1: Creation

When creating new documentation:

| Step | Action |
|------|--------|
| **Template** | Start from the builder's `templates/` — never invent formats |
| **Frontmatter** | Add YAML with `description` and `category` |
| **Chunks** | Write as liftable chunks (see `liftable-chunks.md`) |
| **Versioning** | Pin exact library/framework versions — never "latest" |
| **Validation** | Cross-reference against the actual codebase before committing |

### Phase 2: Synchronization

When the codebase changes, documentation must be updated immediately — not deferred.

**Before coding:**
- Read `docs/state/02_known_issues.md` to avoid triggering known edge cases
- Read `docs/architecture/` to understand current constraints

**During coding (if you change any of these, pause and update docs):**
- Database schema → update `docs/data/01_database_schema.md`
- API contracts → update `docs/data/02_api_contracts.md`
- New dependency → update `docs/architecture/02_tech_stack.md`
- Environment variable → update `docs/infrastructure/01_environment_vars.md`

**After coding:**
- Prepend a changelog entry to `docs/state/01_changelog.md`
- Update `docs/product/02_active_task.md` if the task is complete

### Phase 3: Validation

Periodic checks to detect and fix drift:

| Check | Frequency | Method |
|-------|-----------|--------|
| **Schema accuracy** | Every PR | Compare `01_database_schema.md` against actual schema |
| **Dependency versions** | Monthly | Compare `02_tech_stack.md` against `package.json` |
| **Environment vars** | Every PR adding a var | Verify key exists in `01_environment_vars.md` |
| **Stale content** | Monthly | Flag any doc not updated in 60+ days for review |

### Phase 4: Deprecation

When removing features or changing architecture:

- Mark deprecated sections with `> [DEPRECATED]` blockquote and date
- Move to `docs/state/02_known_issues.md` if the deprecation creates tech debt
- Delete the section entirely after one release cycle

## Staleness Signals

AI agents should flag documentation as potentially stale when:
- A doc references a file path that no longer exists
- Dependency versions in docs don't match `package.json`
- A schema field mentioned in docs is missing from the actual schema
- The doc hasn't been modified in 90+ days while its related code has changed

## Resolution Protocols

| Role | On Finding a Discrepancy |
|------|--------------------------|
| **Architect** | Update docs to match the working codebase |
| **Developer** | Flag the discrepancy to the human — never silently overwrite docs |
| **AI Agent** | Always flag; only update if explicitly authorized |

## AI Rules

- **MUST** update docs immediately when changing schemas, APIs, or dependencies — not deferred
- **MUST** check `docs/state/02_known_issues.md` before starting any coding task
- **MUST** prepend a changelog entry after completing any task
- **MUST** pin exact versions — never use "latest" or version ranges in docs
- **MUST** flag docs as potentially stale when staleness signals are detected
- **MUST NOT** silently resolve doc-code discrepancies without human awareness
- **MUST NOT** delete deprecated content immediately — use the deprecation lifecycle
- **IF** acting as Architect → update docs to match working code
- **IF** acting as Developer → flag discrepancy, do not modify docs unilaterally
- **IF** a doc hasn't been updated in 90+ days → flag for human review
