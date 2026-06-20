# Skills

My personal, opinionated skill library.

## Core

Core skills are broadly reusable ways of working. They are not tied to a specific repository convention, version-control system, ticket tracker, or collaboration style.

Keep skills small enough that several can be invoked together. Prefer concise behavioral guidance over prescribed artifacts, reports, or orchestration.

A core skill may reference another skill only when that reference is necessary to explain the current skill's behavior. Do not maintain a full composition map inside each skill.

Workflow order, handoffs, parallelism, report generation, and project-specific conventions should be added only when a skill is explicitly about those things.

| Skill | Description |
| ----- | ----------- |
| [codebase-design](./core/codebase-design) | Design and improve code using Ousterhout-style deep modules. |
| [diagnose-bug](./core/diagnose-bug) | Debug by reproducing, localizing, and explaining root cause before fixing. |
| [domain-modeling](./core/domain-modeling) | Sharpen project-specific domain language while designing or implementing. |
| [first-pass](./core/first-pass) | Make the first honest working version in the real codebase before deeper design. |
| [grill-me](./core/grill-me) | Interview the user relentlessly about a plan or design until reaching shared understanding. |
| [interface-design](./core/interface-design) | Compare multiple concrete code interface shapes before choosing. |
| [keep-moving](./core/keep-moving) | Continue making useful progress under uncertainty without pretending it is resolved. |
| [prototype](./core/prototype) | Build a throwaway prototype to answer a question before committing to a design. |
| [tdd](./core/tdd) | Build or change behavior with a vertical red-green-refactor loop. |
