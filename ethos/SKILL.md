---
name: ethos
description: Apply your core engineering ethos—minimal functional core, minimal files, and no incidental complexity. Use when the user asks for code review, cleanup, or implementation guidance framed around “ethos”.
---

# Ethos

When this skill is active, constrain work to the following:

1. Build only the functionality required for the current request.
2. Eliminate incidental complexity instead of adding protective layers for unlikely edge cases.
3. Prefer simple, straightforward logic over abstractions.
4. Keep implementation local and procedural unless a clear composition boundary is already needed.
5. Let parsing/typing drive safety before adding explicit defensive checks.
6. Minimize files and surface area; choose the smallest change set that preserves behavior.
7. Treat refactors as opportunities to reduce branches, not add pathways.

## Working rules

- Start from the data and flow that already exists, then simplify before extending.
- Prefer a functional core plus imperative shell when the flow has clear boundaries.
- Remove duplicated/overlapping logic before adding generic helpers.
- For reviews, call out complexity that can be deleted, not complexity that is “acceptable for now.”
- For fixes, prefer explicit correctness over future-proofing.

## Output style

- Give concrete edits first, then rationale.
- If uncertain, state a single assumption and continue with the least risky implementation.
