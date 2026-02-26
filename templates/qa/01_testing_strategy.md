---
target_path: docs/qa/01_testing_strategy.md
category: template
---

# Testing Strategy & Rules

> **Agent Directive:** This document governs how tests are written and executed. Your code must include tests that align perfectly with this strategy.

## 1. Test Runner
- **Unit/Integration:** [Extract test runner from package.json, e.g., Vitest, Jest]
- **E2E:** [Extract e2e framework, e.g., Playwright, Cypress]

## 2. Testing Philosophy
- [State the project's testing philosophy based on existing test files. E.g., "Prioritize Integration Tests over granular Unit Tests for components. Test the behavior, not the implementation details."]
- [State E2E scope. E.g., "E2E tests should cover critical user journeys like Checkout and Authentication."]

## 3. Naming Conventions
- [Extract test file co-location strategy, e.g., "Test files must be co-located with the implementation."]
- File naming: `[Extract extension pattern, e.g., *.test.ts or *.spec.tsx]`.

## 4. Mocking Rules
- [State database testing rules: e.g., "Do not mock the database in integration tests—use a test container or a dedicated test schema."]
- **External APIs:** Mock third-party APIs using the responses found in `02_mock_data.md`.

## 5. Coverage Requirements
- [Extract coverage thresholds from CI or config, e.g., "The CI pipeline enforces an 80% statement coverage threshold."]
