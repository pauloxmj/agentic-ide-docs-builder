---
description: Core formatting rules for AI-readable markdown documentation — liftable chunks, semantic structure, tables over prose.
category: knowledge
---

# AI-First Formatting Standards

Documentation in 2025+ serves two audiences simultaneously: human developers and AI agents. AI models (LLMs) are now a primary way developers discover and interact with product information — they crawl, summarize, and embed docs directly into IDEs and chat interfaces. Structure is the new SEO.

## The AI-First Formatting Rules

### 1. Liftable Chunks

Every section must be **self-contained** — it should make sense when extracted in isolation. AI systems process content as discrete, independent pieces, not continuous narrative.

| Rule | Why |
|------|-----|
| One idea per section | AI retrieval works on chunks; mixing topics degrades accuracy |
| 40-80 word section leads | This is the "liftable" summary AI will cite directly |
| Explicit relationships | State what this section relates to — AI loses implicit connections |

### 2. Semantic Headings

Headings are the primary navigation mechanism for AI parsers.

- Use **descriptive headings** that state the topic clearly (not "Overview" or "Details")
- Use **question-led headings** when applicable — they match how users query AI
- Maintain **strict hierarchy**: H1 for file title, H2 for sections, H3 for subsections — never skip levels

### 3. Tables Over Prose

AI models parse structured data (tables, lists, code blocks) 3-5x more accurately than narrative paragraphs.

- **Use tables** for any data with 2+ dimensions (comparisons, mappings, configs)
- **Use bullet lists** for sequential or categorical information
- **Use code blocks** with language tags for all technical examples
- **Avoid paragraphs** for structured information — convert to tables or lists

### 4. Consistent Terminology

Ambiguous or inconsistent terminology is the #1 cause of AI retrieval failures.

- Define canonical terms once and use them everywhere
- Never use synonyms for the same concept (pick "endpoint" OR "route", not both)
- Use the same casing consistently (e.g., always "AGENTS.md", never "agents.md")

### 5. YAML Frontmatter

Every `.md` file must have frontmatter for machine indexing:

```yaml
---
description: One-line summary for AI and human scanning
category: knowledge | template | guide
---
```

### 6. Concise Summaries

Start every document and major section with a **40-60 word summary** — this is what AI will cite.
- Be factual and specific — no marketing language
- Include the key constraint or takeaway in the first sentence
- Dense noun phrases over verbose sentences

## References

- [Mintlify: Optimizing for AI Agents](https://mintlify.com/blog/ai-agent-experience) — Improving agent experience in docs
- [kapa.ai: AI-Ready Documentation](https://www.kapa.ai/blog/how-to-write-documentation-that-ai-can-actually-use) — Liftable chunks, self-contained sections
- [GitBook: AI-Optimized Documentation](https://www.gitbook.com/blog/geo-guide-optimize-docs-ai-search-llm-ingestion) — Structured content for AI indexing

## AI Rules

- **MUST** write every section as a self-contained liftable chunk
- **MUST** use tables for structured data — never prose paragraphs for comparisons or configs
- **MUST** include 40-60 word summary at the start of every document
- **MUST** use descriptive headings that state the topic — not generic labels
- **MUST** add YAML frontmatter with `description` to every `.md` file
- **MUST** add language tags to all code blocks (e.g., ` ```yaml `, ` ```typescript `)
- **MUST** maintain strict heading hierarchy (H1 → H2 → H3, never skip)
- **MUST NOT** use synonyms for the same concept within a document
- **MUST NOT** write narrative paragraphs when a table or list would work
- **MUST NOT** use vague headings like "Overview", "Details", or "Miscellaneous"
