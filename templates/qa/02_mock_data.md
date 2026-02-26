---
target_path: docs/qa/02_mock_data.md
category: template
---

# Approved Mock Data

> **Agent Directive:** When writing tests or building UI components without a live backend, use *these exact payload structures*. Do not generate random faker data unless explicitly told to.

[Analyze the existing test suite or the product descriptions to generate 1-3 critical mock JSON payloads.]

## 1. [Entity Name, e.g., User Profiles]

### [Sub-type, e.g., Standard User]
```json
{
  "id": "123e4567-e89b-12d3-a456-426614174000",
  "email": "standard@example.com",
  "role": "user"
}
```
