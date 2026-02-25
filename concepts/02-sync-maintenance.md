---
description: State synchronization rules for AI developer agents.
---

<concept id="state-synchronization">
# Auto-Syncing Project State

One of the largest risks of AI development is "state drift"—where the AI writes code that invalidates the architectural documentation, leading to hallucinations in future sessions.

## The Sync Lifecycle

When you (the AI) are acting as a developer on a target project:

1. **Before Coding**: You MUST read `/docs/state/02_known_issues.md` to ensure your proposed solution doesn't trigger a known edge case.
2. **During Coding**: If you alter a database model, an API contract, or introduce a new allowed tech dependency, you MUST pause and update the corresponding file in `/docs/architecture/` or `/docs/data/`.
3. **After Coding**: Upon successfully resolving the Active Task (`/docs/product/02_active_task.md`), you MUST prepend a new summary entry to `/docs/state/01_changelog.md`.

## Resolution Protocols
- If you find a discrepancy between the codebase and the documentation, and you are acting as the Architect role, you MUST update the documentation to match the *working* codebase.
- If you are acting as a Developer role, you MUST point out the discrepancy to the human rather than silently overwriting the docs.
</concept>
