# Agentic IDE Docs Builder RAC Database

> A **Retrieval-Augmented Context (RAC)** database and template kit for instructing AI coding agents to generate bulletproof project ground truth documentation.

## What This Is

This project is a highly dense **context database designed strictly for AI agents**. It uses explicit XML tagging (`<concept>`, `<template>`) to provide deterministic boundaries for AI parsers, eliminating conversational fluff and reducing hallucination.

The core workflow involves giving an AI agent three things:
1. The context from this repository (the RAC database).
2. The codebase of a target project you want to document.
3. Specific instructions provided in your manual prompt (e.g., "Analyze my codebase and generate the ground truth docs using the agentic-ide-docs-builder templates").

Using this combination, the AI will extract the `/docs/` templates from here and perfectly fill them out based on the realities of the target codebase.

## The RAC Core Schema

Read `RAC-SCHEMA.md` to understand the XML boundaries. The repository is structured to separate concerns entirely:

| Directory | Tag Strategy | Purpose |
|-----------|--------------|---------|
| `concepts/` | `<concept>` | Theoretical rules on how to document architecture and maintain state. |
| `templates/` | `<template>` | Raw, copy-pasteable markdown structures for scaffolding the target `/docs` folder. |

## Repository Structure

```
agentic-ide-docs-builder/
├── README.md                 ← You are here
├── AGENTS.md                 ← Project-level context injector
├── RAC-SCHEMA.md             ← The strict XML parsing ruleset
├── AGENT-INSTRUCTIONS.md     ← Paste into your AI Assistant prompt
│
├── concepts/                 ← Knowledge on how to write good documentation
└── templates/                ← Scaffolding structures to inject into target projects
```

## How AI Agents Use This

If you are an AI:
1. Parse `RAC-SCHEMA.md` immediately.
2. Treat `concepts/` as your theoretical foundation.
3. Extract `templates/` to output the final result into the target codebase.

If you are a Human:
1. Provide `AGENT-INSTRUCTIONS.md` to your custom assistant (Claude Project, Custom GPT, etc.).
2. Upload this entire repo as its knowledge base.
3. Ask it to generate the ground-truth `/docs` for your active project!
