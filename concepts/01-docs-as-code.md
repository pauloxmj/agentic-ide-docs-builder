---
description: The core philosophy of Docs-as-Code for AI agents.
---

<concept id="docs-as-code">
# Docs-as-Code Architecture

- **Definition**: Documentation is written in Markdown, stored in the same Git repository as the source code, and subjected to the same Pull Request review process as production code.
- **Why it matters for AI**: If documentation lives in a separate portal (like Notion or Confluence), an AI coding agent inside an IDE cannot read it. By placing the documentation at `[project-root]/docs/`, the AI gets perfect, immediate context retrieval.
- **The Rule of Ground Truth**: In an agentic workflow, the `/docs` folder IS the codebase. If the code contradicts the `/docs`, the code is considered broken unless a human explicitly authorizes a change to the `/docs`.

## Key Principles for Generation
When generating these docs for a target project:
1. **Be Exact**: Do not generalize. If the database uses PostgreSQL `jsonb` columns, say exactly that, not "JSON storage".
2. **Be Dense**: Use bullet points and tables. Omit conversational filler.
</concept>
