---
description: Comprehensive guide to writing effective AGENTS.md entrypoint files — the universal standard for AI coding agent context.
category: knowledge
---

# AGENTS.md Authoring Guide

AGENTS.md is the universal, open standard for guiding AI coding agents. Used by 60,000+ open-source projects, it provides a predictable, dedicated location for the context and instructions AI agents need to work effectively on your project. Think of it as a README for machines.

## What AGENTS.md Is (and Is Not)

| AGENTS.md | README.md |
|-----------|-----------|
| For AI coding agents | For human developers |
| Build steps, test commands, conventions | Quick starts, project descriptions |
| Precise, dense, machine-optimized | Conversational, marketing-friendly |
| Can be nested per subdirectory | Typically one per repo |

## Required Sections

Every AGENTS.md must include these sections, following the progressive disclosure pattern:

### 1. System Context (H1 + blockquote)
A 2-3 sentence summary of the project following the llms.txt pattern:
- H1 with the project name
- Blockquote with the project's core purpose and tech stack
- Key constraints (language, framework versions)

```markdown
# Project Name

> A [type of project] built with [tech stack]. [One key constraint].
```

### 2. Setup Commands
Exact, copy-pasteable commands for the agent to bootstrap the environment:
- Install dependencies
- Start dev server
- Run tests
- Run linter/formatter

### 3. Code Style and Conventions
Dense rules the agent must follow:
- Language settings (e.g., TypeScript strict mode)
- Naming conventions
- File structure patterns
- Import ordering

### 4. Testing Instructions
What testing framework, how to run tests, minimum coverage expectations.

## Recommended Sections

### 5. Directory Map
A table or tree showing where key files and directories live — helps agents navigate without scanning the entire repo.

### 6. Architecture Constraints
High-level patterns the agent must follow (e.g., "feature-sliced design", "offline-first", "DDD").

### 7. Documentation Pointers
Where the agent should look for deeper context (e.g., `/docs/`, `.agent/skills/`).

### 8. Non-Negotiable Guardrails
Hard rules that override everything:
- Zero hallucination policy
- Database immutability
- Scope adherence
- Conflict resolution protocol

## Optional Sections

### 9. PR Guidelines
How the agent should structure commits and PRs.

### 10. Security Considerations
What the agent must never do (e.g., output secrets, disable auth).

## Nested AGENTS.md Pattern

For monorepos or large projects, place additional AGENTS.md files in critical subdirectories. AI agents automatically read the closest file for context:

```
project/
├── AGENTS.md              ← Root-level: global conventions
├── packages/
│   ├── api/
│   │   └── AGENTS.md      ← API-specific: endpoints, auth patterns
│   └── web/
│       └── AGENTS.md      ← Web-specific: component patterns, styling
```

## Anti-Patterns to Avoid

| Anti-Pattern | Why It Fails |
|-------------|-------------|
| Generic boilerplate ("write clean code") | Wastes tokens, provides no actionable context |
| Duplicating linter rules | Linters enforce these automatically — focus on judgment calls |
| Long narrative explanations | AI parses bullet points and tables 3-5x more accurately |
| Missing version numbers | Without exact versions, AI will hallucinate compatible APIs |
| Mixing global and project concerns | Creates confusion about what's universal vs. codebase-specific |

## References

- [agents.md Official Spec](https://agents.md) — The open standard, 60k+ repos

## AI Rules

- **MUST** include system context, setup commands, code style, and testing instructions at minimum
- **MUST** follow progressive disclosure — essential info in AGENTS.md, details in linked docs
- **MUST** use exact version numbers for all frameworks and libraries
- **MUST** make every section self-contained (liftable chunk pattern)
- **MUST** use the llms.txt heading pattern (H1 + blockquote + sections)
- **MUST NOT** use generic boilerplate that provides no project-specific value
- **MUST NOT** duplicate rules that linters/formatters enforce automatically
- **MUST NOT** write narrative paragraphs when bullet points or tables would work
- **IF** monorepo → use nested AGENTS.md files for subdirectory-specific context
- **IF** guardrail conflicts with user prompt → flag to human, do not silently override
