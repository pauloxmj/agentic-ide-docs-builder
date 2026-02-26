---
description: Docs-as-Code philosophy — documentation stored in Git, reviewed in PRs, and optimized for both human and AI consumption.
category: knowledge
---

# Docs-as-Code Architecture

Documentation is written in Markdown, stored in the same Git repository as the source code, and subjected to the same Pull Request review process as production code. In 2025+, LLMs are a primary interface for documentation — making structure and AI-readability as important as human readability.

## Core Principles

| Principle | Rule |
|-----------|------|
| **Co-location** | Docs live at `[project-root]/docs/` — never in external portals (Notion, Confluence) |
| **Ground Truth** | If code contradicts `/docs` → the code is broken unless a human authorizes a docs change |
| **Version Control** | Docs are reviewed in PRs with the same rigor as production code |
| **AI-First** | Structure is the new SEO — AI agents parse docs as their primary context source |
| **Dense Format** | Bullet points, tables, code blocks — never narrative paragraphs for structured data |

## Why Co-location Matters for AI

If documentation lives in a separate portal, an AI coding agent inside an IDE cannot read it. By placing docs in the repo, the AI gets perfect, immediate context retrieval without external tool dependencies or MCP connections.

## The Dual-Audience Contract

Every document must serve both audiences simultaneously:

| Audience | Needs |
|----------|-------|
| **Human developers** | Scannable, well-organized, contextual explanations |
| **AI agents** | Self-contained chunks, consistent terminology, structured data, YAML metadata |

The good news: these needs align. Dense, structured, well-organized docs serve both audiences better than narrative prose.

## References

- [llmstxt.org](https://llmstxt.org) — Standard for AI-readable documentation files
- [agents.md](https://agents.md) — Universal entrypoint standard for AI coding agents

## AI Rules

- **MUST** store all documentation in the Git repository at `[project-root]/docs/`
- **MUST** treat `/docs` as the single source of truth for project specifications
- **MUST** write documentation optimized for both human scanning and AI parsing
- **MUST NOT** place documentation in external portals — it must be accessible to IDE agents
- **IF** code and docs disagree → flag to human, do not silently update either
