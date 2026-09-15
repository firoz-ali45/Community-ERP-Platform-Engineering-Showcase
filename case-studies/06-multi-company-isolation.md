# 06 — Multi-company isolation

## Problem
Multi-company ERP silently leaks documents across companies when rules are incomplete.

## Observed symptom
Users see or report another company’s records; exports bypass UI filters.

## Forensic reasoning
Test negative access on models, reports, and integrations—not only list views.

## Root cause / engineering challenge
Company scoping treated as UX rather than authorization.

## Minimal safe solution
Default-deny record rules, propagated `company_id`, report/PDF checks, and automated negative tests.

## Validation method
Denied read/write proofs across companies; report generation under least privilege.

## Engineering lesson
If export ignores company, isolation is fiction.

## Public-safe evidence
Synthetic rule sketch in `examples/`.

## What remains private
Real rule XML and tenant matrices.
