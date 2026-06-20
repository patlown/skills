---
name: diagnose-bug
description: Debug by proving the failure before fixing it. Use when investigating bugs, failing tests, regressions, flaky behavior, production symptoms, or any request where root cause is unclear and a guessed fix would be risky.
---

# Diagnose Bug

Do not fix first. Establish a causal explanation before changing behavior.

## Process

1. Reproduce or observe the failure.
2. Minimize the case until the signal is small enough to reason about.
3. Localize the code path that can explain the behavior.
4. State the root cause in terms of behavior, not just file location.
5. Only then choose a fix strategy.

If a failure cannot be reproduced, narrow the uncertainty instead of inventing a fix. Identify what evidence is missing and what observation would distinguish the likely causes.

## Evidence

Use the strongest available evidence:

- failing tests
- logs, traces, screenshots, or repro steps
- code paths and data flow
- recent diffs or dependency changes
- production configuration and environment differences

Prefer direct observation over plausible stories.

## Fixing

When implementing the fix, keep it tied to the proven cause. Add or adjust tests when they can lock the behavior without coupling to internals.

Do not broaden into cleanup or architecture work unless the bug proves the current shape is part of the cause.
