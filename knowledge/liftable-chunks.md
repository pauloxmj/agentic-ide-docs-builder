---
description: The liftable chunks pattern — writing self-contained documentation sections that AI can extract, cite, and reason about independently.
category: knowledge
---

# Liftable Chunks Pattern

A "liftable chunk" is a self-contained documentation section that makes complete sense when extracted from its surrounding context. This is the foundational pattern for AI-readable documentation because AI retrieval systems (RAG, vector search) process content as discrete, independent pieces — not as continuous narrative.

## Why Chunks Matter

AI documentation retrieval works by:
1. **Splitting** documents into chunks (typically at heading boundaries)
2. **Embedding** each chunk as a vector in a search index
3. **Retrieving** the most relevant chunks for a given query
4. **Presenting** those chunks to the LLM as context

If a chunk depends on surrounding context to make sense, the AI will misinterpret it or hallucinate missing information.

## The Anatomy of a Good Chunk

| Element | Guideline |
|---------|-----------|
| **Lead summary** | 40-60 words stating the key fact — this is what AI will cite |
| **Body** | Supporting details in bullets or tables — never narrative prose |
| **Explicit scope** | States what this section covers and what it doesn't |
| **Self-contained** | Makes sense without reading any other section |
| **Single purpose** | Answers one question or addresses one topic |

## How to Write Liftable Chunks

### 1. One Section = One Question
Each section should answer a single question. If you find yourself covering two topics, split into two sections.

**Bad**: "## Database" (covers schema AND migrations AND queries)
**Good**: "## Database Schema", "## Migration Strategy", "## Query Patterns"

### 2. State Relationships Explicitly
AI loses implicit connections. If Section B depends on Section A, say so directly.

**Bad**: "As mentioned above, use the same pattern here."
**Good**: "This follows the Repository Pattern defined in `docs/architecture/01_system_design.md`."

### 3. Lead with the Answer
Start every section with the conclusion or key fact (inverted pyramid). Details follow.

**Bad**: "There are several approaches to error handling. First, consider..."
**Good**: "All errors MUST use the `AppError` class from `src/shared/errors.ts`. This ensures consistent error codes across the API."

### 4. Size Guide

| Chunk Type | Target Size | Example |
|-----------|------------|---------|
| **Definition** | 40-80 words | "What is offline-first architecture?" |
| **How-to** | 80-150 words | "How to add a new API endpoint" |
| **Reference** | Fits in one table | Schema definitions, config mappings |
| **Decision** | 60-100 words | "Why we chose Zustand over Redux" |

## References

- [kapa.ai: Writing Documentation AI Can Use](https://www.kapa.ai/blog/how-to-write-documentation-that-ai-can-actually-use) — Canonical source on liftable chunks

## AI Rules

- **MUST** write every documentation section as a self-contained chunk
- **MUST** start each section with a 40-60 word lead summary stating the key fact
- **MUST** limit each section to a single topic or question
- **MUST** state relationships to other sections explicitly — never use "as mentioned above"
- **MUST** use inverted pyramid structure — conclusion first, details after
- **MUST NOT** write sections that depend on surrounding context to be understood
- **MUST NOT** combine multiple topics in a single section
- **IF** a section exceeds 200 words → split it into subsections or separate files
