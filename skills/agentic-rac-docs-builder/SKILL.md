<template target_path="skills/agentic-rac-docs-builder/SKILL.md">
---
name: agentic-rac-docs-builder
description: Use this skill whenever requested to create, update, or manage project documentation. It guarantees all documentation adheres strictly to the Retrieval-Augmented Context (RAC) schema and formatting rules for flawless AI parseability.
---

# Agentic RAC Docs Builder Skill

This skill ensures that all changes, additions, or modifications to a repository's documentation follow the exact RAC constraints set out in the agentic-ide-docs-builder knowledge base.

## Context Prerequisites

Before executing any docs-related task, you MUST read the following foundational context from the master RAC reference database (`/home/paulo/Repositories/agentic-ide-docs-builder`):

1. **Schema Rules**: Parse `/home/paulo/Repositories/agentic-ide-docs-builder/RAC-SCHEMA.md` first. This defines the strict XML parsing boundaries (`<concept>`, `<template>`).
2. **Concepts**: Review relevant `.md` files in `/home/paulo/Repositories/agentic-ide-docs-builder/concepts/` to inform your theoretical understanding.
3. **Templates**: When creating new docs, extract the correct scaffolding structures from `/home/paulo/Repositories/agentic-ide-docs-builder/templates/`.

## Core Execution Invariants

1. **Strictly RAC Tolerant Formatting**:
   - Write dense, hierarchical bullet points. No conversational fluff or narrative filler.
   - Use correct YAML frontmatter for all documentation (`.md`) files to index descriptions and metadata.
   - Use `<concept id="...">` for declarative knowledge, architecture guidelines, or principles.
   - Use `<template target_path="...">` if outputting raw scaffolding that another AI should use.

2. **Source of Truth Sync**:
   - Never deviate from the structural templates found in the target's `/templates/` directory.
   - If a document is updated, apply identical RAC-compliant structure and AI-oriented terseness to that update.
   - Ensure you follow the specific template formatting for Architecture, Data, QA, Standards, State, and Workflows if applicable.

3. **Validation**:
   - Before completing documentation edits or creation, verify that your new document has standard frontmatter, the correct headings, no conversational preamble, and appropriate tags if necessary.
   - All rules established in `RAC-SCHEMA.md` are mandatory and non-negotiable.
</template>
