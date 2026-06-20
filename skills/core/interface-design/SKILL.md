---
name: interface-design
description: Design a code module interface by comparing multiple concrete shapes before choosing. Use when deciding what a function, class, package, service, public API, or module surface should expose, especially when callers, invariants, or misuse risk matter.
---

# Interface Design

Design the interface more than once before choosing.

This skill is about code module interfaces, not visual UI design. An interface includes everything a caller must know: signatures, types, invariants, ordering, errors, configuration, side effects, and performance expectations.

## Process

1. Inspect actual callers and likely callers.
2. Identify what the module should hide from callers.
3. Sketch at least two meaningfully different interface shapes.
4. For each option, show a small interface sketch and caller sketch.
5. Compare options by depth, information hiding, ease of correct use, misuse risk, locality, and fit with existing code.
6. Choose or synthesize one shape before implementing.

Prefer caller code over implementation code in sketches. The question is what callers must know and how much leverage the interface gives them.

## Good Options Differ Structurally

Different options should disagree about shape, not just names:

- one entry point versus several operations
- command style versus stateful object
- explicit result object versus exceptions
- narrow specialized interface versus broader general-purpose interface
- dependency passed in versus hidden behind an internal seam

Do not compare only syntax.
