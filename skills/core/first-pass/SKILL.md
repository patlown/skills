---
name: first-pass
description: Make the first honest working version of a change in the real codebase before deeper design or cleanup. Use when the user wants to get behavior working directly, learn from implementation feedback, or intentionally defer architecture and reusability until after a concrete pass.
---

# First Pass

Make the requested behavior work in the real codebase first. Use implementation as a way to learn the real shape of the problem.

## Rules

1. Start near the code being changed.
2. Prefer direct, procedural code over new abstractions.
3. Accept temporary duplication, local branching, and imperfect placement when they help reveal the real shape.
4. Do not introduce reusable helpers, module boundaries, or broad restructuring until the working behavior proves they are needed.
5. Do only the restructuring required to keep the change understandable and working.
6. Keep the diff easy to inspect.
7. Stop after the first honest working version; deeper design and cleanup belong to a later pass.

## When To Switch

If the request is asking whether a design should exist at all, build a prototype instead of touching the production path.

If the intended behavior is still unresolved, ask or reason through the decision before coding.

If tests are the best way to pin the behavior while implementing, write the smallest useful test first and keep the loop vertical.
