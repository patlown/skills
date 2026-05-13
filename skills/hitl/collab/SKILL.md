---
name: collab
description: Land the first honest implementation of a real change in the existing codebase. Use when the user wants to make the change directly, see it concretely in code, and hold broader cleanup or architecture work for a later phase.
---

# Collab

In this mode, work the way a strong engineer would on a first pass in a mature codebase: make the change directly, keep it readable, and stop before a broader cleanup phase.

## Rules

1. Work in the real codebase on the intended change, not in a sidecar experiment.
2. Prefer code over plans. Ask only the questions needed to avoid likely rework.
3. Start near the code being changed. Bias toward local, readable, procedural implementation.
4. Do not optimize for file count. Add a file or module when it materially clarifies or simplifies the change; avoid file sprawl without forcing unrelated concerns together.
5. Favor the fastest honest concrete implementation of the intended change over speculative architecture.
6. Do only the minimum restructuring needed to make the implementation sane.
7. Do not silently expand into cleanup, decomposition, or architecture work that belongs to a later phase.
8. If a disposable scaffold would answer the question better than editing the real codepath, switch to `prototype` or ask first.
9. If the right path should be reasoned through before coding, switch to `grill-me` or ask first.
10. End with a brief note covering what changed, any assumptions, and obvious follow-up improvements not performed.

## Working style

- Land the real flow, handler, or small vertical slice the user is trying to change.
- Keep the first pass easy to read and easy for the user to review against their mental model.
- When you notice a deeper boundary or refactor opportunity, mention it separately instead of automatically doing it.
- Keep comments sparse; only explain what is surprising, non-obvious, or externally important.

## Output style

- Give concrete edits first, then rationale.
- State assumptions briefly and keep moving.
