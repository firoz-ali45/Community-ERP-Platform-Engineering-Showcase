# Community ERP Platform — Engineering Showcase

An independent public engineering reference for building and operating a **production-grade ERP** on **Odoo Community Edition**, with emphasis on security, governance, release discipline, testing evidence, and compliance-engineering *principles*.

This repository is **not** the private application source tree. It documents architecture, controls, and forensic methods that keep complex ERP delivery auditable and safe.

> **Not affiliated with, endorsed by, or certified by Odoo S.A. or the Odoo Community Association (OCA).**

## What Community ERP Platform is

**Community ERP Platform** is an engineering line for multi-company ERP operations on Odoo Community Edition 17. It treats ERP delivery as a governed system: identity of what runs in each environment must be provable, privileged changes must be fail-closed, and sensitive domains (tax, HR, inventory regulation, authentication) must be isolated by design.

## Engineering philosophy

1. **Security first** — least privilege, multi-company isolation, secret hygiene, and explicit threat boundaries.
2. **Governance first** — written precedence, change control, and UAT protection beat ad-hoc hotfix culture.
3. **Evidence over assertion** — claims about runtime require identity proofs and bounded diagnostics.
4. **Minimum change, maximum proof** — prefer the smallest correction that restores invariants for *all* future workloads.
5. **Sovereignty without reckless forking** — pin upstream dependencies; extend via overlays, not silent edits to vendor trees.

## Whole-platform architecture (conceptual)

```text
                    ┌─────────────────────────┐
                    │   Git source of truth    │
                    │  (governed release line) │
                    └───────────┬─────────────┘
                                │ promote (manual, fail-closed)
           ┌────────────────────┼────────────────────┐
           ▼                                         ▼
   ┌───────────────┐                         ┌───────────────┐
   │ Management    │                         │ Production    │
   │ Sandbox       │  ←── isolation ───────→ │ (protected)   │
   │ (UAT / prove) │                         │               │
   └───────────────┘                         └───────────────┘
```

Domain modules (Quality, Accounting, Inventory, POS, HR/Payroll, e-invoicing, integrations, etc.) share the same governance and release machinery. No single domain owns the platform.

## Security-first principles

- Separate **Sandbox** and **Production** identities and promote paths.
- Treat authentication, SSO boundaries, ACL/record-rule design, and report/PDF output as security surfaces.
- Never place live credentials in Git; CI must reference secret stores by name only.
- Prefer read-only forensic bridges for incident evidence over improvisational operator access.

See [`docs/security/`](docs/security/).

## Governance-first delivery

- Executable rules for humans and automation (precedence, freezes, branch/write discipline).
- Change control that distinguishes documentation, configuration, and business-logic risk.
- Management UAT as a process freeze: push ≠ deploy.

See [`docs/governance/`](docs/governance/).

## DevOps and release discipline

- **Push is not deploy.** Promotion is an explicit, authorized action against a named commit.
- Release identity is a chain: source → commit → promotion → runtime authority record.
- CI gates are fail-closed; weakening gates to “make green” is a governance failure.

See [`docs/devops/`](docs/devops/).

## Testing and evidence

- Tests and gates produce artifacts that can be reviewed without trusting narrative alone.
- Post-change validation must show *user-facing or runtime* effects where feasible, not only row counts.

See [`docs/testing/evidence-standards.md`](docs/testing/evidence-standards.md).

## Compliance engineering principles

KSA-related domains (e-invoicing, labor, regulated inventory, payroll reporting) are discussed here as **lifecycle, control, and isolation methodology**—not as proprietary implementation or signing material.

See [`docs/compliance/`](docs/compliance/).

## Dependency sovereignty

Upstream Odoo/OCA/vendor modules should be pinned and treated as pristine. Behavior changes belong in first-party extension layers. Public material here describes the *policy*, not vendored trees.

See case study [`04-dependency-sovereignty.md`](case-studies/04-dependency-sovereignty.md).

## Forensic engineering

When schedules, queues, or promotions “look wrong,” prove process and identity state before rewriting business logic. Read-only diagnostics and classification trees prevent speculative patches.

See [`case-studies/09-read-only-forensic-diagnostics.md`](case-studies/09-read-only-forensic-diagnostics.md).

## What this repository contains

| Area | Contents |
|------|----------|
| `docs/` | Architecture, security, governance, DevOps, testing, domain principles |
| `case-studies/` | Rewritten engineering narratives (whole platform) |
| `examples/` | Obviously synthetic configuration snippets |
| `diagrams/` | Placeholder for architecture diagrams |
| `evidence/` | Policy for redacted evidence only |

## What this repository deliberately does not contain

- Private ERP application source (`custom_addons` and equivalents)
- Vendor/upstream source trees
- Database dumps, filestore, backups
- Live credentials, keys, signing material
- Operable production/sandbox infrastructure runbooks
- Customer or employee personal data
- Proprietary compliance algorithms or secret-handling code

## Third-party attribution

Upstream projects (Odoo Community, OCA modules, and other vendors) are **referenced**, not redistributed here. See [`NOTICE`](NOTICE).

## Security reporting

See [`SECURITY.md`](SECURITY.md).

## Contributing

Documentation and synthetic-example improvements are welcome under [`CONTRIBUTING.md`](CONTRIBUTING.md). Do not submit private customer artifacts or live secrets.
