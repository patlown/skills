---
name: codebase-design
description: Design and improve code using Ousterhout-style deep modules. Use when shaping module interfaces, evaluating architecture, finding shallow code, deciding where behavior should live, placing seams, improving testability, or making code easier to change.
---

# Codebase Design

Design deep modules: useful behavior behind small interfaces. The aim is leverage for callers, locality for maintainers, and tests that exercise behavior through the same surface callers use.

## Language

A **module** is any unit of code with callers and an implementation: a function, class, package, route, slice, or service.

An **interface** is everything a caller must know to use a module correctly. It includes signatures, types, invariants, required ordering, error behavior, configuration, side effects, and performance expectations.

An **implementation** is the code hidden behind the interface.

A **seam** is a place where behavior can vary without editing the caller.

An **adapter** is one concrete implementation used at a seam.

## Principles

- Prefer deep modules: small interfaces hiding substantial behavior.
- Treat depth as leverage, not line-count ratio.
- Hide information callers should not need.
- Use the deletion test: if deleting a module makes complexity disappear, it was probably shallow; if the complexity reappears across callers, it was doing real work.
- The interface is the test surface. Tests reaching past it are evidence that the module shape may be wrong.
- Do not introduce seams speculatively. If there is only one adapter and no concrete pressure for another, prefer direct code.
- Architecture work should improve locality, leverage, or testability. Do not propose cleanup for its own sake.

## What To Inspect

Look for:

- callers that must know too much
- behavior scattered across many files
- pass-through modules whose interfaces are nearly as complex as their implementations
- duplicated concepts with slightly different names
- tests that mock or reach through internals because the public interface is awkward
- changes that require touching many places for one concept

Explore the codebase to answer questions before asking the user.

## Designing Or Refactoring

If asked to design, explain the design pressure and recommend a shape.

If asked to implement, make the smallest refactor that improves depth, locality, or testability. Avoid broad cleanup not tied to a specific pressure.

For dependency-specific deepening guidance, read [DEEPENING.md](DEEPENING.md).
