# walmart-cart · Cart Service

Session-based shopping cart gRPC service. Stores and retrieves cart items per user session, with pluggable storage backends: in-memory, Redis, Spanner, and AlloyDB.

## Stack
- **Language:** C# / .NET 8
- **Framework:** gRPC (`Grpc.AspNetCore`)

## API
Implements `CartService` from `demo.proto`:
- `AddItem(AddItemRequest) → Empty`
- `GetCart(GetCartRequest) → Cart`
- `EmptyCart(EmptyCartRequest) → Empty`

## Running locally
```bash
dotnet run
```
Service listens on port `7070` by default (`CART_SERVICE_PORT`).

Configure the storage backend via `REDIS_ADDR`, `SPANNER_PROJECT`, or AlloyDB env vars. Defaults to in-memory if none are set.

## Dependencies
None — connects to infra (Redis / Spanner / AlloyDB) only, no internal service calls.
