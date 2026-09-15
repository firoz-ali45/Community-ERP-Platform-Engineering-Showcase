# Change control

## Classification

| Change type | Risk | Expectation |
|-------------|------|-------------|
| Docs / diagrams | Lower | Still review for secret leakage |
| Synthetic examples | Lower | Fictional values only |
| CI/governance tooling | Medium | Fail-closed; no weaken-to-pass |
| Application business logic | High | Explicit scope, tests, UAT |
| Auth / ACL / tax / payroll | Critical | Named authorization |

## Minimum package for high-risk changes

1. Problem statement with evidence
2. Smallest patch set
3. Tests / gates
4. Promotion of an exact commit
5. Runtime identity verification
