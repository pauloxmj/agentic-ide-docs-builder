---
description: AI-friendly structural frameworks for documentation constraints.
---

<concept id="diataxis-framework">
# The Diátaxis Framework for AI

When generating documentation, you must understand the four distinct quadrants of informational needs (Diátaxis):

1. **Tutorials (Learning-Oriented)**: How to accomplish a goal from scratch.
   - *In our RAC structure*: Rarely needed. This is implicit in the codebase.
2. **How-To Guides (Problem-Oriented)**: Steps to solve a specific problem.
   - *In our RAC structure*: Mapped to `/docs/workflows/`. Highly actionable steps for branch management, PR submission, etc.
3. **Reference (Information-Oriented)**: Dry, dense facts mapping the system.
   - *In our RAC structure*: Mapped to `/docs/architecture/`, `/docs/data/`, and `/docs/infrastructure/`. Absolute technical truth.
4. **Explanation (Understanding-Oriented)**: The "Why" behind the system.
   - *In our RAC structure*: Mapped to `/docs/product/01_prd.md` and `/docs/standards/`.

## AI Parsing Advantage
AI Models are exceptionally good at parsing **Reference** material. When writing documentation templates, lean heavily into Reference structures (tables, schemas, strict types) rather than long Explanations.
</concept>
