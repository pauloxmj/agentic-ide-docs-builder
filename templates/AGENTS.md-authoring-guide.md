---
description: Production-ready template and checklist for authoring AGENTS.md entrypoint files for any project.
category: template
target_path: AGENTS.md
---

# [Project Name]

> [One-sentence description of the project]. Built with [tech stack with exact versions]. [Key architectural constraint].

## Setup Commands

```bash
# Install dependencies
[package-manager] install

# Start development server
[package-manager] [dev-command]

# Run tests
[package-manager] test

# Run linter
[package-manager] [lint-command]
```

## Code Style

- [Language]: [strict/flexible] mode
- [Quote style], [semicolons yes/no]
- [Naming convention for files]
- [Naming convention for functions/classes]
- [Import ordering rules]

## Testing

- **Framework**: [test framework + version]
- **Run**: `[test command]`
- **Coverage minimum**: [percentage]
- **Rules**:
  - [Testing convention 1]
  - [Testing convention 2]

## Project Structure

```
[project-root]/
├── [src-dir]/           ← [description]
├── [components-dir]/    ← [description]
├── [docs-dir]/          ← [description]
├── [config-files]       ← [description]
└── AGENTS.md            ← This file
```

## Architecture

- **Pattern**: [e.g., Feature-sliced, DDD, MVC]
- **State management**: [library + pattern]
- **Data layer**: [approach]
- **Key constraint**: [e.g., offline-first, real-time, serverless]

## Documentation

| Location | Purpose |
|----------|---------|
| `docs/architecture/` | System design and tech stack |
| `docs/data/` | Database schema and API contracts |
| `.agent/skills/` | AI-specific skills and capabilities |
| `.agent/rules/` | AI behavioral constraints |

## Non-Negotiable Guardrails

1. **Zero hallucination** — Never invent data not present in the codebase
2. **Docs-as-Code** — All documentation lives in `/docs/` inside this repo
3. **Scope adherence** — Only modify files within the requested scope
4. **Conflict resolution** — If instructions conflict, flag to human — do not guess

## Key Dependencies

| Dependency | Version | LLM Docs |
|-----------|---------|----------|
| [Framework] | [exact version] | [llms.txt URL if available] |
| [Library] | [exact version] | [llms.txt URL if available] |

## PR Guidelines

- One concern per PR
- Reference related issues
- All tests must pass
- Include summary of changes
