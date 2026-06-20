# Ethos

This repository is guided by a simple software design philosophy:

1. Build only the functionality required for the current request.
2. Prefer simple, straightforward logic over abstractions.
3. Eliminate incidental complexity instead of adding protective layers for unlikely futures.
4. Let code teach you where the real boundaries are before committing to architecture.
5. Avoid file sprawl, but do not force unrelated concerns together just to keep file count low.
6. Treat implementation, prototyping, and refactoring as distinct phases when that keeps the work clearer.
7. Let parsing, types, and executable flow carry safety before adding explicit defensive checks.
8. Comments should explain only what is surprising, non-obvious, or externally important.

## Skill Design

Core skills are broadly reusable ways of working. They should be useful across projects, tools, version-control systems, ticket trackers, and documentation conventions.

Keep skills small enough that several can be invoked together. Prefer concise behavioral guidance over prescribed artifacts, reports, or orchestration.

A core skill may reference another skill only when that reference is necessary to explain the current skill's behavior. Do not maintain a full composition map inside each skill.

Workflow order, handoffs, parallelism, report generation, and project-specific conventions should be added only when a skill is explicitly about those things.

These are repo-level values, not a standalone skill.
