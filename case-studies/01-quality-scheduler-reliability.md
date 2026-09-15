# 01 — Quality scheduler reliability

## Problem
Recurring quality work appeared stalled in the UI: next run in the past, last run looking inconsistent with automatic progression.

## Observed symptom
Operators concluded “the schedule is broken” and relied on manual generation.

## Forensic reasoning
Before changing recurrence logic, inspect whether the **scheduler process** can run at all: cron thread configuration, cron last/next advancement, and whether recent tasks were manual vs automatic.

## Root cause / engineering challenge
Runtime configuration disabled cron execution (`max_cron_threads` effectively zero). Recurrence math was not the primary fault. Manual generation updated last-run style fields without advancing the automatic next-run bookkeeping—by design—creating a misleading UI narrative.

## Minimal safe solution
Restore a non-zero cron thread default in the environment entrypoint that generates application configuration, so **all** schedules regain automatic execution—not a one-row data patch for a single schedule.

## Validation method
After governed Sandbox promotion of the exact commit: confirm cron last/next advancing, automatic task creation (non-manual occurrence keys), and future next-run for the previously stuck schedule class.

## Engineering lesson
Process-level disablement masquerades as domain bugs. Prove cron health before rewriting business logic.

## Public-safe evidence
Redacted before/after: cron advancing; next-run moved forward; automatic task created.

## What remains private
Hosts, database names, assignee identities, SQL, container inventories, live SHAs as operable runbooks.
