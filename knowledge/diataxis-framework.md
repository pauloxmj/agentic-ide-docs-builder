---
description: The Diátaxis framework adapted for AI-generated documentation — four quadrants mapped to doc categories with AI optimization notes.
category: knowledge
---

# The Diátaxis Framework for AI

The Diátaxis framework defines four distinct quadrants of informational needs. When generating documentation, each quadrant maps to specific doc categories and requires different formatting strategies for optimal AI consumption.

## The Four Quadrants

| Quadrant | Orientation | Doc Category | AI Optimization |
|----------|-------------|-------------|-----------------|
| **Tutorials** | Learning | Rarely needed — implicit in codebase | Low priority; only generate if explicitly requested |
| **How-To Guides** | Problem-solving | `docs/workflows/` | Numbered step lists; each step = one action |
| **Reference** | Information | `docs/architecture/`, `docs/data/`, `docs/infrastructure/` | Tables, schemas, strict types — AI's strongest format |
| **Explanation** | Understanding | `docs/product/01_prd.md`, `docs/standards/` | Bullet-point rationales; avoid long-form prose |

## AI Parsing Performance by Quadrant

AI models perform best with **Reference** material. When writing docs, lean heavily into Reference structures:

| Format | AI Accuracy | Use For |
|--------|------------|---------|
| Tables | ★★★★★ | Schema definitions, config mappings, comparisons |
| Code blocks | ★★★★★ | API contracts, example payloads, commands |
| Numbered lists | ★★★★ | Step-by-step procedures, ordered workflows |
| Bullet lists | ★★★★ | Properties, rules, constraints |
| Short paragraphs | ★★★ | Context explanations (keep under 60 words) |
| Long paragraphs | ★★ | Avoid — split into bullets or tables |

## AI Rules

- **MUST** categorize every generated document into one of the four Diátaxis quadrants
- **MUST** favor Reference-style formatting (tables, schemas, types) over narrative Explanation
- **MUST** write How-To Guides as numbered step lists — one action per step
- **MUST NOT** generate Tutorial-style documentation unless explicitly requested
- **IF** a document spans multiple quadrants → split it into separate files
