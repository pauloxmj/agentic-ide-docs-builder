---
description: The llms.txt standard — a markdown-based format for providing LLM-friendly content at website and project roots.
category: knowledge
---

# The llms.txt Standard

The llms.txt standard, proposed by Jeremy Howard (co-founder of Answer.AI) in September 2024, provides a structured markdown file at the root of a website or project that helps LLMs and AI agents understand and index content effectively. By late 2025, companies including Mintlify, Anthropic, and Cursor have adopted it.

## Why llms.txt Exists

LLMs face a critical limitation: context windows are too small to handle most websites in entirety. Converting complex HTML (with navigation, ads, JavaScript) into LLM-friendly text is imprecise. llms.txt provides a curated, structured summary that AI can parse immediately.

## The Format Specification

A compliant llms.txt file contains these sections in this exact order:

| Section | Required | Description |
|---------|----------|-------------|
| **H1** | ✅ Yes | Project or site name (the only required section) |
| **Blockquote** | Recommended | Short summary with key information for understanding the file |
| **Body sections** | Optional | Detailed information (paragraphs, lists — no headings) |
| **H2 file lists** | Optional | Sections with markdown links `[name](url): description` |
| **## Optional** | Special | URLs here can be skipped for shorter context |

### Minimal Example

```markdown
# Project Name

> Brief description of what this project does and its key technologies.

## Documentation
- [Architecture](docs/architecture.md): System design and component interactions
- [API Reference](docs/api.md): Endpoint contracts and payloads

## Optional
- [Changelog](docs/changelog.md): Recent modifications
```

## How llms.txt Relates to AGENTS.md

| Standard | Purpose | Audience |
|----------|---------|----------|
| **llms.txt** | Website/docs discoverability for AI crawlers | External AI systems indexing your site |
| **AGENTS.md** | Project-level instructions for coding agents | AI agents working inside your codebase |

They are complementary: llms.txt is external-facing (web), AGENTS.md is internal-facing (repo). Both use the same H1 + blockquote + file list pattern.

## Companion Files

The standard also recommends:
- **`llms-full.txt`**: Single markdown file compiling all site text (expanded context)
- **`.md` versions of pages**: Every HTML page offers a `.md` variant at the same URL + `.md`

## References

- [llmstxt.org](https://llmstxt.org) — Official specification

## AI Rules

- **MUST** follow the exact section order: H1 → blockquote → body → H2 file lists
- **MUST** use the `[name](url): description` format for file lists
- **MUST** place the `## Optional` section last for skippable content
- **MUST NOT** use headings other than H1 and H2 in the llms.txt file
- **IF** generating docs for a web project → create both llms.txt and AGENTS.md
- **IF** context length is a concern → use the `## Optional` section for secondary content
