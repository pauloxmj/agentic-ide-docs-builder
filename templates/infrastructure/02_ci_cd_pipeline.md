<template target_path="docs/infrastructure/02_ci_cd_pipeline.md">
# CI/CD Pipeline & Deployment Strategy

> **Agent Directive:** This document explains how code moves from a developer's machine into production. When creating workflows or scripts, ensure they align with these constraints (e.g., test thresholds, linting rules).

## 1. Hosting Provider
[Read the action configs / vercel config / dockerfile to determine where this gets hosted: e.g., Vercel (Frontend), AWS ECS (Backend), Supabase (Database)]

## 2. Continuous Integration ([Platform, e.g., GitHub Actions])
Every Pull Request to `main` must pass the following checks sequentially:
[List the exact steps defined in the pipeline configuration files, e.g.:]
1. **Linter:** `[Extract exact npm format command]`
2. **Type Check:** `[Extract typecheck command]`
3. **Unit Tests:** `[Extract test command]`
4. **E2E Tests:** `[Extract e2e command]`

## 3. Deployment Flow
[Extract the deployment triggers. E.g.]
1. **Feature Branch:** Commits trigger isolated unit tests.
2. **Pull Request to `main`:** Triggers full CI pipeline. A [Preview URL mechanism if any] is generated.
3. **Merge to `main`:** Triggers automatic production build and deployment.
4. **Database Migrations:** Run automatically pre-deployment via [Extract ORM push command].

## 4. Containerization ([Docker/Podman/None])
[If a Dockerfile exists, summarize its multi-stage build process.]
</template>
