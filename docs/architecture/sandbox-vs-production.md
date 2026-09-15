# Sandbox vs Production

## Problem

ERP teams often blur “test” and “live,” causing accidental mutation of Management UAT or Production during routine engineering.

## Separation model

| Concern | Sandbox | Production |
|---------|---------|------------|
| Purpose | Prove changes under UAT | Serve live operations |
| Mutability | Governed promotions only | Highly restricted |
| Identity | Distinct runtime authority record | Distinct runtime authority record |
| Diagnostics | Prefer read-only bridges | Prefer read-only; destructive ops exceptional |

## Rules of thumb

1. A green CI build on a branch does **not** change Sandbox.
2. Sandbox promotion must name an exact commit and an authorization reason.
3. Production remains untouched by Sandbox tooling.
4. Shared hosts (if any) must still enforce container/database identity fail-closed checks.

## What remains private

Operable hostnames, addresses, container inventories, and credential stores are not documented here.
