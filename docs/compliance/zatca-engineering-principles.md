# ZATCA engineering principles (public)

## What we publish

Architecture and gating principles for e-invoicing engineering programs.

## What we never publish here

- Signing implementations
- Certificate/private key material
- cryptographic enrollment identifiers
- Secret vault contents
- Production API credentials
- Proprietary XML transforms beyond public standards references

## Principles

1. Clearance/reporting modes are explicit configuration, not ambient magic.
2. Queue/retry behavior must be observable without dumping secrets.
3. Cryptographic material lives outside Git.
4. Sandbox proofs do not automatically authorize Production claims.
5. Changes to e-invoicing paths require named authorization and regression evidence.
