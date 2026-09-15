# 09 — Read-only forensic diagnostics

## Problem
Incident response demands SSH/SQL from non-technical owners, raising error and exposure risk.

## Observed symptom
Blocked workstation SSH; incomplete local evidence; pressure to “just fix it.”

## Forensic reasoning
Reuse existing authorized CI remote access patterns for **read-only** collection with fail-closed environment identity checks.

## Root cause / engineering challenge
Missing governed observability bridge—not missing tribal knowledge.

## Minimal safe solution
Manual diagnostic workflow: prove Sandbox identity, SELECT-only queries, bounded logs, redact secrets, no restarts/deploys.

## Validation method
Static safety scan of diagnostic tooling; successful evidence collection without mutation seals.

## Engineering lesson
Observability is a product control, not an owner chore.

## Public-safe evidence
Abstract diagnostic sections A–G (identity, process, cron, schedule, time, logs).

## What remains private
Real workflows, hosts, and raw logs.
