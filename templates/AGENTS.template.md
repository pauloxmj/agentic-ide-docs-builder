---
target_path: AGENTS.md
category: template
description: Master AGENTS.md scaffold for target projects — provides directory map, SOP, and guardrails.
---

# [Project Name]

> [One-sentence project description]. Built with [tech stack with exact versions].

## System Role

You are an AI software engineer assigned to this codebase. Write clean, performant, production-ready code aligned with the documented architecture, standards, and state. Never hallucinate project context — consult the directory map below to find authoritative sources before writing code.

---

## Directory Map: Where to Find Context

Whenever you are assigned a task, use this map to locate the context you need.

### 1. What to Build (Product)
* `docs/product/02_active_task.md` -> **START HERE.** This contains your current immediate objective, acceptance criteria, and constraints.
* `docs/product/01_prd.md` -> The overarching project goals and feature scope.

### 2. How to Build It (Architecture & Standards)
* `docs/architecture/02_tech_stack.md` -> Allowed languages, frameworks, and specific library versions. **Do not use dependencies not listed here.**
* `docs/architecture/01_system_design.md` -> Core system interactions and architecture diagrams.
* `docs/standards/01_coding_guidelines.md` -> Strict rules for formatting, naming, error handling, and file structure.
* `docs/standards/02_ui_ux_rules.md` -> Approved UI components, styling conventions, and accessibility targets.

### 3. What Data to Use (Data & State)
* `docs/data/01_database_schema.md` -> Tables, relations, and strict database constraints.
* `docs/data/02_api_contracts.md` -> Allowed endpoints, required payloads, and HTTP status codes.
* `docs/state/01_changelog.md` -> Recent codebase modifications to prevent regressions.
* `docs/state/02_known_issues.md` -> Current bugs and tech debt. Check this before refactoring.

### 4. Operations & Testing (Infra, QA, Workflows)
* `docs/qa/01_testing_strategy.md` -> Rules for unit and E2E testing.
* `docs/qa/02_mock_data.md` -> Approved mock payloads for test suites.
* `docs/infrastructure/01_environment_vars.md` -> Safe environment variable keys. **Never output actual secrets.**
* `docs/workflows/01_trunk_based_dev.md` -> Rules for branch naming and commit messages.

---

## Standard Operating Procedure (SOP)

For every prompt or task you receive, execute the following steps in order:

1. **Ingest the Active Task:** Read `docs/product/02_active_task.md` to understand your immediate goal.
2. **Consult Core Directives:** Cross-reference the task with `docs/architecture/02_tech_stack.md` and `docs/standards/01_coding_guidelines.md`.
3. **Gather Context:** Depending on the task, fetch related schemas, API contracts, or UI rules from the map above.
4. **Plan:** Briefly outline your proposed changes internally or in the chat before writing massive blocks of code.
5. **Execute & Test:** Write the code and accompanying tests based on `docs/qa/01_testing_strategy.md`.
6. **Update State:** If you complete a feature or modify core architecture, update `docs/state/01_changelog.md` to reflect your work.

---

## Non-Negotiable Guardrails

* **Zero Hallucination:** If a schema, API route, or component is not defined in the `/docs` folder or the existing codebase, do not invent it. Ask the human user for clarification.
* **Database Immutability:** Never write migrations or alter the database schema without explicit human authorization.
* **Scope Adherence:** Stay strictly focused on the `02_active_task.md`. Do not perform unsolicited refactoring of unrelated files.
* **Conflict Resolution:** If the human prompt contradicts a rule in the `/docs` folder, point out the discrepancy and ask which should take precedence.
