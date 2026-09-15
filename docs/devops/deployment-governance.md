# Deployment governance

## Core rule

**Push ≠ deploy.**

Promotion into Sandbox (and any higher environment) is a separate, authorized control-plane action that targets an exact commit.

## Fail-closed inputs (pattern)

- Full commit identity
- Non-empty authorization ticket/reason
- Environment allowlists (Sandbox-only tooling must refuse Production identities)

## Outcomes to record

- Pre-promote gates
- Promote result
- Post-promote smoke
- Runtime authority record update
