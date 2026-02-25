<template target_path="docs/workflows/02_pr_guidelines.md">
# Pull Request Guidelines

> **Agent Directive:** Before you suggest to the human that a task is complete and ready for a Pull Request, you must autonomously verify this checklist.

## Pre-Flight Checklist

1. **Self-Review:** Have you re-read your own code against `standards/01_coding_guidelines.md`?
2. **Leftover Logs:** Did you remove all debugging `console.log` or `print` statements?
3. **Linter & Types:** Run your linter and type-checker. Did it pass with zero errors?
4. **Tests:** Are all tests passing? If you added a feature, did you add tests for it?
5. **State Update:** Did you prepend an entry to `state/01_changelog.md` summarizing your work?

## Writing the PR Description
If the user asks you to draft a PR description, use this template:

```markdown
## Description
[Brief summary of what was changed and why]

## Related Tickets
Resolves #[Ticket Number/Active Task]

## Type of Change
- [ ] Bug fix
- [ ] New feature

## Verification
- [ ] Linter passes
- [ ] Tests pass
- [ ] Changelog updated
```
</template>
