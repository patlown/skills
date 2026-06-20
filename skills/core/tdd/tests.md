# Good And Bad Tests

## Good Tests

Good tests verify observable behavior through real interfaces.

```typescript
test("user can checkout with a valid cart", async () => {
  const cart = createCart();
  cart.add(product);

  const result = await checkout(cart, paymentMethod);

  expect(result.status).toBe("confirmed");
});
```

Characteristics:

- Tests behavior users or callers care about
- Uses the public interface
- Survives internal refactors
- Describes what the system does, not how it does it
- Has one clear reason to fail

## Bad Tests

Implementation-detail tests couple to internal structure.

```typescript
test("checkout calls paymentService.process", async () => {
  const mockPayment = jest.mock(paymentService);

  await checkout(cart, payment);

  expect(mockPayment.process).toHaveBeenCalledWith(cart.total);
});
```

Red flags:

- Mocking internal collaborators
- Testing private methods
- Asserting internal call counts or ordering
- Breaking when behavior is unchanged
- Test names that describe how the code works instead of what behavior exists

Prefer verifying through the public interface:

```typescript
// Bad: bypasses the interface to verify persistence.
test("createUser saves to database", async () => {
  await createUser({ name: "Alice" });
  const row = await db.query("SELECT * FROM users WHERE name = ?", ["Alice"]);
  expect(row).toBeDefined();
});

// Better: verifies behavior through another public operation.
test("createUser makes the user retrievable", async () => {
  const user = await createUser({ name: "Alice" });
  const retrieved = await getUser(user.id);
  expect(retrieved.name).toBe("Alice");
});
```
