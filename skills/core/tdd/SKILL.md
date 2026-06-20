---
name: tdd
description: Build or change behavior with a vertical red-green-refactor loop. Use when behavior is clear enough to express as tests, especially for bug fixes, behavior-heavy features, regressions, refactors that must preserve behavior, edge-case logic, permissions, money, scheduling, parsing, or public interface contracts.
---

# Test-Driven Development

Use tests as the steering wheel when behavior certainty matters.

Use this skill when the behavior to build or preserve is clear enough to express as an observable test. If the intended behavior is still unsettled, resolve that before writing speculative tests.

## Loop

1. Write one failing test for one observable behavior.
2. Make the smallest code change that passes it.
3. Repeat for the next behavior.
4. Refactor only while green.

Do not write all tests first and then all implementation. That horizontal slice produces tests for imagined behavior. Work vertically: one behavior, one failing test, one implementation step.

## Test Shape

Tests should verify public behavior, not private implementation. Prefer integration-style tests through real interfaces.

Read [tests.md](tests.md) when judging whether a test is good or too coupled to implementation.

Read [mocking.md](mocking.md) before mocking dependencies.

## Local Refactor

After green, clean the code touched by the current behavior:

- remove duplication revealed by the current tests
- improve names and local structure
- keep tests on the public behavior

Do not expand into broad architecture cleanup unless the user asked for it.
