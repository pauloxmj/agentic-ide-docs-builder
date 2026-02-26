---
target_path: docs/data/02_api_contracts.md
category: template
---

# API Contracts & Endpoints

> **Agent Directive:** This document defines the expected request/response shapes for all API routes. Do not alter existing contracts without explicit human permission. New features must adhere to established payload structures.

## Authentication & Headers
[Define how routes are protected globally based on codebase middleware analysis]

## Base URL
[Determine base API URL]

---

[For every major API endpoint mapped in the codebase, generate a block like below:]

## Resource: `/[ResourceName]`

### `[METHOD] /[path]`
**Description:** [What it does]  
**Status Codes:** [Possible returned codes]  
**Payload** (If applicable):
```json
{
  "key": "type"
}
```
**Returns:**
```json
{
  "key": "type"
}
```
