---
description: Semantic parser tags and formatting rules for the RAC Database.
---

# RAC Schema & Parser Guidelines

This database operates on the principles of **Retrieval-Augmented Context (RAC)**. The knowledge base is heavily optimized for zero-hallucination processing by an AI agent acting as a Documentation Engine.

When searching this knowledge base, the AI must locate and extract information strictly bounded by the following XML tags:

## Core Schema Tags

### `<concept id="[unique-id]">`
- **Definition**: Fundamental concepts, architectural principles, or general knowledge for writing technical documentation.
- **Usage**: Used to establish the theoretical rules of engagement (e.g., Docs-as-Code, Diátaxis framework).
- **Example**: `<concept id="docs-as-code">`

### `<template target_path="[path]">`
- **Definition**: A strictly formatted markdown template designed for copy-pasting into a target project.
- **Usage**: The exact structural foundation an AI should use when generating the ground-truth documentation files for a repository. The `target_path` attribute dictates exactly where in the destination project the file must be written (e.g., `target_path="docs/architecture/01_system_design.md"`).

## Structural Constraints
1. **No Conversational Fluff**: Knowledge is presented in dense, hierarchical bullet points.
2. **YAML Frontmatter**: All nodes (`.md` files) use YAML frontmatter to index descriptions and metadata.
3. **Strict Bounds**: If information is not within one of the tags defined above, it is considered supplementary context and *not* authoritative RAC data.
