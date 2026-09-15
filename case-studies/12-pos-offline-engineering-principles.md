# 12 — POS offline engineering principles

## Problem
POS must continue selling when connectivity or fiscal services degrade, without corrupting later sync.

## Observed symptom
Duplicate submissions, blocked tills, or unclear offline queues.

## Forensic reasoning
Separate local integrity, sync idempotency, and fiscal submission stages.

## Root cause / engineering challenge
Offline mode designed as “best effort” without durable identity keys.

## Minimal safe solution
Durable local records, idempotent sync, explicit offline policies, and observability that avoids secret leakage.

## Validation method
Scripted offline/online transitions in Sandbox; assert no duplicate fiscal identities.

## Engineering lesson
Offline is a distributed systems problem inside a retail UX.

## Public-safe evidence
Principle checklist.

## What remains private
Offline engines, endpoints, and credentials.
