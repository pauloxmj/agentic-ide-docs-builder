---
target_path: docs/architecture/01_system_design.md
category: template
---

# System Architecture & Design

> **Agent Directive:** This document defines the high-level architecture and component interactions. Use this to understand the boundary context of the feature you are building. Do not deviate from these structural patterns without human approval.

## 1. High-Level Architecture
[Analyze the codebase and describe if this is a monolith, microservices, serverless, etc. Provide a conceptual Mermaid diagram if possible.]

## 2. Core Operational Flow
[Describe the primary flow of data from the client to the database and back based on the routers/controllers discovered.]

## 3. Directory Map
[Briefly explain the project's source code directory structure (e.g., `/src/components` vs `/src/hooks`) based on existing patterns.]

## 4. Cross-Cutting Concerns
- **Authentication:** [How auth is handled, e.g., JWT in HttpOnly cookies, based on the codebase]
- **Authorization:** [How roles/permissions are checked]
- **Caching Strategy:** [e.g., Redis for session data, CDN for assets]
