<template target_path="docs/infrastructure/01_environment_vars.md">
# Environment Variables

> **Agent Directive:** This file defines the *keys* and *purposes* of environment variables required for the project. **Never place actual secret values (API keys, DB passwords) in this file.** When writing code that interacts with `process.env`, ensure the key is documented here.

## 1. Local Development (`.env.local`)
| Key | Type | Requirement | Purpose |
| :--- | :--- | :--- | :--- |
| `[ENV_VAR_KEY_FOUND_IN_CODE]` | [Type] | [Required/Optional] | [Reason for existence] |
| `[E.g., DATABASE_URL]` | `String` | `Required` | `PostgreSQL connection string` |

## 2. Production Overrides (`.env.production`)
- `[ENV_VAR_EXPLICIT_TO_PROD]`: [Purpose]

## 3. Validation Rules
The project uses [Determine what validation library is used, e.g., Zod / t3-env / custom] to validate environment variables at startup. If you add a new key here, you MUST update the validation schema located at `[Path to validation schema]`.
</template>
