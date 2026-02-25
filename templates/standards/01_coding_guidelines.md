<template target_path="docs/standards/01_coding_guidelines.md">
# Coding Guidelines

> **Agent Directive:** This document dictates how code should look and behave. Adhere strictly to these patterns to ensure consistency across the codebase.

## 1. Naming Conventions
[Analyze the codebase for naming conventions]
- **Variables/Functions:** [e.g., camelCase, prefix booleans with `is` or `has`]
- **Constants:** [e.g., UPPER_SNAKE_CASE]
- **Components:** [e.g., PascalCase]

## 2. File Structure & Imports
[Analyze the codebase for import sorting and file extensions]
- **Imports:** [e.g., React first, absolute paths second, relative paths last]
- **File Naming:** [e.g., index.ts for exports, ComponentName.tsx for UI]

## 3. Error Handling
[Analyze how the codebase throws/catches/returns errors]
- [e.g., Wrap all async chunks in try/catch, use a custom `AppError` class, no silent failures]

## 4. Modern Paradigms
- [e.g., Prefer pure functions, do not mutate React state directly, strict null checks]
</template>
