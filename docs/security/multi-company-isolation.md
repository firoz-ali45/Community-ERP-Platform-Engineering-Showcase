# Multi-company isolation

## Intent

In multi-company ERP, “same database, different companies” is a security boundary—not a UI filter convenience.

## Principles

1. **Default deny across companies** for sensitive models unless a rule explicitly allows.
2. **Company fields propagate** through related documents (orders, moves, quality tasks, payslips).
3. **Reports and PDFs** must inherit the same isolation—export is an access path.
4. **Integrations** must not become a cross-company data pump.
5. **Tests** should include negative cases (user A must not read company B).

## Synthetic sketch

See [`examples/synthetic-multi-company-rule.xml`](../../examples/synthetic-multi-company-rule.xml). It uses fictional model names only.

## What remains private

Real `ir.rule` XML, group matrices, and tenant-specific exceptions stay in private source control.
