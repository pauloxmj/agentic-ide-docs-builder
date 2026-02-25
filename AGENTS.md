# AGENTS.md

<system_context>
Welcome to the Agentic IDE Docs Builder RAC Database! 
This project is a Retrieval-Augmented Context (RAC) database designed strictly for AI agents. 
By providing this repository as context alongside a target project's codebase, AI systems can use this knowledge to automatically generate and maintain a bulletproof, human-and-AI-readable documentation structure for the target project.
</system_context>

## RAC Parsing Instructions

If you are an AI assistant entering this repository to assist a developer, **start by reading:**
`RAC-SCHEMA.md`

This file defines the strict XML parsing boundaries (`<concept>`, `<template>`) required to extract semantic knowledge without hallucination or context pollution.

## Repository RAC Structure

Our knowledge base is mathematically divided for deterministic semantic extraction:

1. **`concepts/`**: Universal knowledge on Docs-as-Code and architecture documentation, wrapped in `<concept>` tags.
2. **`templates/`**: Production-ready starter templates for mapping a project's Architecture, Data, QA, Standards, State, and Workflows, bounded by `<template>` tags.
