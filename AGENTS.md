---
description: AI-first knowledge base for generating and maintaining project documentation using Docs-as-Code and AI-optimized formatting principles.
---

# Agentic IDE Docs Builder

> A Retrieval-Augmented Context (RAC) knowledge base that teaches AI agents to analyze a target project's codebase and scaffold or update its `/docs` folder. The output is a bulletproof, single source of truth for all human and AI developers.

## Knowledge Base Map

Read files in order of relevance to your current task.

| Directory | Purpose | When to Read |
|-----------|---------|--------------|
| `knowledge/` | Foundational principles and formatting standards | Before generating any documentation |
| `templates/` | Production-ready markdown scaffolds for every doc category | When creating new doc files for a target project |
| `skills/` | Executable skill instructions for the docs builder | When invoked as an agent skill |

### Knowledge Files — Principles
- [docs-as-code.md](knowledge/docs-as-code.md) → Docs live in Git, reviewed like code, AI-first
- [diataxis-framework.md](knowledge/diataxis-framework.md) → Four quadrants (Tutorial, How-To, Reference, Explanation) with AI optimization
- [doc-maintenance-lifecycle.md](knowledge/doc-maintenance-lifecycle.md) → Creation → sync → validation → deprecation lifecycle

### Knowledge Files — AI Formatting Standards
- [ai-first-formatting.md](knowledge/ai-first-formatting.md) → Liftable chunks, tables over prose, semantic headings, YAML frontmatter
- [liftable-chunks.md](knowledge/liftable-chunks.md) → Self-contained sections AI can extract and cite independently
- [agents-md-authoring.md](knowledge/agents-md-authoring.md) → How to write effective AGENTS.md entrypoint files
- [llms-txt-standard.md](knowledge/llms-txt-standard.md) → The llms.txt standard for AI-discoverable documentation

### Template Categories
- `templates/AGENTS.template.md` → Master AGENTS.md scaffold for target projects
- `templates/AGENTS.md-authoring-guide.md` → Guide/checklist for authoring AGENTS.md files
- `templates/architecture/` → System design, tech stack
- `templates/data/` → Database schema, API contracts
- `templates/infrastructure/` → Environment vars, CI/CD pipeline
- `templates/product/` → PRD, active task tracker
- `templates/qa/` → Testing strategy, mock data
- `templates/standards/` → Coding guidelines, UI/UX rules
- `templates/state/` → Changelog, known issues
- `templates/workflows/` → Git flow, PR guidelines

---

## Content Formatting Standard

All generated documentation must follow these formatting rules (detailed in `knowledge/ai-first-formatting.md`):

1. **Liftable chunks** — Every section must be self-contained and make sense when read in isolation
2. **Tables over prose** — Use tables for any structured data with 2+ dimensions
3. **40-60 word leads** — Start every document and section with a concise summary
4. **Semantic headings** — Descriptive headings that state the topic, never generic labels
5. **YAML frontmatter** — Every `.md` file must have `description` in frontmatter
6. **Code block language tags** — Always specify the language (` ```yaml `, ` ```typescript `)
7. **Consistent terminology** — Same term for the same concept throughout all docs
8. **Exact versions** — Pin framework/library versions, never "latest"

---

## Standard Operating Procedures

This builder supports three workflows. Use the decision table to pick the right one.

### When to Use Which Workflow

| Situation | Workflow |
|-----------|----------|
| No `/docs` folder exists yet | **Implement** — scaffold from scratch |
| `/docs` exists but a section is wrong or outdated | **Modify** — edit specific files |
| Codebase changed (new deps, schema changes, new features) | **Update** — sync docs to match code |

### Workflow 1: Implement (Scaffold New Docs)

1. **Read Knowledge** — Read all files in `knowledge/` to understand the principles
2. **Select Templates** — Read templates matching the documentation scope; each has `target_path` in its frontmatter
3. **Analyze Target Codebase** — Extract real, factual data from source code, configs, and existing docs
4. **Generate Documentation** — Fill template placeholders `[...]` with factual data. Follow the Content Formatting Standard above
5. **Include Reference Links** — When the target project uses libraries or frameworks that provide LLM-optimized documentation (`llms.txt`, `/docs/llms.txt`, or dedicated markdown APIs), include those links in the relevant sections
6. **Generate AGENTS.md** — Use `templates/AGENTS.md-authoring-guide.md` and `knowledge/agents-md-authoring.md` to create the project's `AGENTS.md` entrypoint
7. **Validate Output** — Run the validation checklist below

### Workflow 2: Modify (Edit Existing Docs)

1. **Read the target file** — Understand its current content and structure
2. **Read `knowledge/ai-first-formatting.md`** — Ensure edits follow formatting rules
3. **Make targeted edits** — Change only the sections that are incorrect or outdated
4. **Preserve structure** — Do not reorganize or rename files unless explicitly asked
5. **Update changelog** — Prepend an entry to `docs/state/01_changelog.md`
6. **Validate Output** — Run the validation checklist below

### Workflow 3: Update (Sync Docs to Code Changes)

Follow the sync triggers defined in `knowledge/doc-maintenance-lifecycle.md`:

1. **Identify what changed** — Schema? API? Dependency? Environment variable?
2. **Update the matching doc** — See the sync mapping table in `doc-maintenance-lifecycle.md`
3. **Check for cascading changes** — If a schema changed, does the API contract doc also need updating?
4. **Update changelog** — Prepend an entry to `docs/state/01_changelog.md`
5. **Flag any ambiguity** — If the code change is unclear, flag to human rather than guessing
6. **Validate Output** — Run the validation checklist below

### Validation Checklist

- [ ] Every file has YAML frontmatter with `description`
- [ ] Every section is a self-contained liftable chunk
- [ ] No narrative paragraphs where tables/lists would work
- [ ] All placeholders `[...]` filled with real data or marked `TBD — Requires Human Input`
- [ ] No hallucinated schemas, APIs, or library names
- [ ] Exact version numbers for all dependencies
- [ ] `AGENTS.md` follows the llms.txt pattern (H1 + blockquote + sections)
- [ ] LLM-optimized doc links included for key dependencies where available

---

## AI Rules

- **MUST** read `knowledge/` files before generating any documentation
- **MUST** use template structures from `templates/` — never invent doc formats
- **MUST** follow the Content Formatting Standard for all generated files
- **MUST** fill bracketed placeholders `[...]` with factual data from the target codebase
- **MUST** write `TBD — Requires Human Input` for any data not verifiable in the codebase
- **MUST** include LLM-optimized documentation links (`llms.txt` URLs, markdown API docs) in generated docs when the target project's dependencies provide them
- **MUST** generate an AGENTS.md entrypoint following the authoring guide
- **MUST NOT** hallucinate schemas, APIs, or library names not found in the target codebase
- **MUST NOT** modify database schemas without explicit human authorization
- **MUST NOT** write narrative paragraphs when tables, bullet lists, or code blocks would work
- **IF** the target codebase contradicts existing docs → flag the discrepancy to the human
- **IF** a template category is irrelevant to the target project → skip it, do not generate empty stubs
- **IF** a dependency provides `llms.txt` or LLM-optimized docs → include the URL as a reference
