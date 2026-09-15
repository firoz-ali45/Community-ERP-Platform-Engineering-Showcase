# Architecture overview

## Intent

Describe how a Community Edition ERP platform is structured so that multiple business domains share one governed runtime without collapsing security boundaries.

## Logical layers

1. **Presentation** — web client, POS UI, portals (where enabled).
2. **Application** — Odoo modules for finance, stock, quality, HR, POS, integrations.
3. **Security** — groups, record rules, company scoping, report access.
4. **Integration** — outbound/inbound adapters with explicit trust boundaries.
5. **Platform** — PostgreSQL, application workers, job/cron execution, object storage/filestore.
6. **Control plane** — Git, CI gates, promotion workflows, runtime identity records.

## Domain map (non-exhaustive)

| Domain | Engineering focus |
|--------|-------------------|
| Accounting | Controls, journals, tax posting discipline |
| Sales / Purchase | Document flow, approvals, auditability |
| Inventory | Traceability, valuation, warehouse isolation |
| POS | Offline resilience, local integrity, sync |
| Quality | Scheduling, evidence, assignment |
| HR / Payroll | Privacy, statutory reporting controls |
| E-invoicing | Lifecycle gates (no secret material here) |
| Regulated goods | Lot/expiry/control principles |
| Auth / SSO | Boundary between ERP and satellite apps |

## Design rules

- Prefer extension modules over editing upstream.
- Keep Sandbox and Production promote paths distinct.
- Treat cron/workers as part of correctness, not “ops trivia.”
