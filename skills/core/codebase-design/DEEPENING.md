# Deepening

How to deepen a cluster of shallow modules safely, given its dependencies. This assumes the vocabulary from [SKILL.md](SKILL.md): module, interface, seam, adapter.

## Dependency Categories

### In-Process

Pure computation, in-memory state, no I/O.

Deepen directly. Move behavior behind the new interface and test through that interface.

### Local-Substitutable

Dependencies with local test stand-ins, such as an in-memory filesystem or local database.

Deepen when the stand-in exists and can run in the test suite. Keep the seam internal unless production behavior genuinely varies.

### Remote But Owned

Your own services across a network boundary.

Define a narrow interface at the seam. Keep the logic in the deep module. Use one adapter for the real transport and another for tests or local execution.

### True External

Third-party services you do not control.

Put a narrow interface between your code and the external service. Tests should use a fake or mock adapter at that seam.

## Seam Discipline

A seam is a place where behavior can vary without editing the caller.

Do not introduce a seam just because one could exist. A seam earns its keep when behavior genuinely varies there: production versus test, one provider versus another, local versus remote, or old path versus new path.

Internal seams are allowed inside a deep module. Do not expose them through the module's interface just because tests use them.

## Testing Strategy

Replace brittle tests instead of layering new tests on top of them.

Old unit tests around shallow helpers may become waste once behavior is covered at the deepened module's interface. Prefer tests that assert observable behavior through the interface and survive internal refactors.
