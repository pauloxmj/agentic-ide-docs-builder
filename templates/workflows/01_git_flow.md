---
target_path: docs/workflows/01_trunk_based_dev.md
category: template
---

# Git Workflow & Branching Strategy

> **Agent Directive:** When using the terminal to interact with Git, you must follow these branch naming and commit message conventions.

## 1. Branch Naming
- **Features:** `feat/ticket-id-short-description`
- **Fixes:** `fix/ticket-id-short-description`
- **Chores:** `chore/update-dependencies`

## 2. Commit Message Format
We use Conventional Commits.
- `feat: [Description]` for new features.
- `fix: [Description]` for bug fixes.
- `refactor: [Description]` for code changes.
- `style: [Description]` for formatting changes.
- `test: [Description]` for tests.
- `chore: [Description]` for build process changes.

## 3. Pulling & Pushing
Always pull `main` and rebase your feature branch before pushing to avoid complex merge commits.
