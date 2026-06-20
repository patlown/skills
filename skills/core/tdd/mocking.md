# Mocking

Mock at system boundaries, not inside your own design.

Good candidates:

- third-party APIs
- email, payment, messaging, or analytics providers
- time and randomness
- filesystem or database access when a real local substitute is too expensive

Avoid mocking:

- your own classes or modules
- internal collaborators
- private methods
- code you control and can exercise through a real interface

## Design Boundary Interfaces

Pass external dependencies in instead of creating them deep inside the code.

```typescript
// Easier to test.
function processPayment(order, paymentClient) {
  return paymentClient.charge(order.total);
}

// Harder to test.
function processPayment(order) {
  const client = new StripeClient(process.env.STRIPE_KEY);
  return client.charge(order.total);
}
```

Prefer specific operations over one generic fetcher with conditional mock logic.

```typescript
// Better: each operation has one shape.
const api = {
  getUser: (id) => fetch(`/users/${id}`),
  getOrders: (userId) => fetch(`/users/${userId}/orders`),
  createOrder: (data) => fetch("/orders", { method: "POST", body: data }),
};

// Worse: every test mock must understand endpoint strings and options.
const api = {
  fetch: (endpoint, options) => fetch(endpoint, options),
};
```
