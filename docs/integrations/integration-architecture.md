# Integration architecture (public)

## Pattern

```text
External system ──adapter──▶ ERP API / webhook boundary ──▶ domain services
                                      │
                                      ▼
                              authn/authz + idempotency
```

## Principles

1. Explicit trust boundaries and credential stores.
2. Idempotent ingestion where duplicates are likely.
3. Observability without logging secrets or full payloads of personal data.
4. Company scoping on every write path.
5. Historical connectors (legacy eras) must not re-enter public examples with live endpoints.
