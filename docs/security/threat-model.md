# Threat model (summary)

## Assets

- Financial documents and tax-relevant artifacts
- Inventory and regulated goods records
- Employee and payroll-adjacent data
- Authentication sessions and SSO tokens
- Integration credentials (never stored in Git)

## Adversaries / failure modes

- Accidental Production mutation by automation
- Privilege escalation via weak record rules
- Secret leakage through logs, examples, or CI output
- Supply-chain drift from unmanaged upstream edits
- Speculative business-logic patches that miss process-level faults

## Mitigations (patterns)

- Fail-closed environment identity checks
- Secret managers + redaction
- Separation of promote workflows from ordinary pushes
- Pristine upstream policy + overlays
- Read-only forensic diagnostics before code changes

This document is educational. It is not a penetration-test report.
