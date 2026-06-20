---
name: domain-modeling
description: Sharpen project-specific domain language while designing or implementing. Use when terminology, concepts, states, transitions, invariants, or relationships are fuzzy, overloaded, or important to code names, data shape, tests, UI language, or future conversations.
---

# Domain Modeling

Actively clarify the domain model while work is happening. The goal is shared language that makes code, tests, and conversations more precise.

## Moves

1. Gather language from the user, code, tests, data, docs, and UI.
2. Challenge fuzzy or overloaded terms.
3. Separate domain concepts from implementation accidents.
4. Identify important relationships, states, transitions, and invariants.
5. Stress-test the model with concrete scenarios and edge cases.
6. Cross-check user claims against code when the code can answer.

Prefer concrete names from the domain over names from the current implementation when the implementation name is accidental.

Do not create a taxonomy for its own sake. Resolve only distinctions that affect behavior, data shape, interface design, tests, or future communication.

## CONTEXT.md

`CONTEXT.md` is allowed, but it must stay small. It is a glossary, not a spec.

Use an existing `CONTEXT.md` if the repo has one. If not, create a root `CONTEXT.md` only when the first term is worth recording.

Create or update `CONTEXT.md` only when a term is:

- project-specific
- likely to recur
- clarified through the current work
- useful for naming code, tests, docs, or future conversations

Do not add:

- implementation details
- generic programming concepts
- plans, TODOs, meeting notes, or scratchpad thoughts
- every noun mentioned once
- terms whose meaning is still unresolved

Definitions should be one or two sentences. Add "Avoid" synonyms only when a wrong synonym is likely to cause confusion.

Keep the format simple:

```md
# Context

## Terms

### Term

One or two sentences defining the project-specific meaning.

Avoid: Ambiguous synonym, misleading synonym.
```

Do not create ADRs as part of this skill.
