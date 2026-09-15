# Quality scheduler reliability (principles)

## Invariant

When the Quality cron is healthy, due schedules (`next_run` at or before now) must be consumed, and automatic processing must advance `next_run`.

## Common misdiagnosis

UI symptoms (past `next_run`, confusing `last_run`) are often blamed on recurrence math while **process-level cron execution** is disabled or stalled.

## Engineering response pattern

1. Prove environment identity.
2. Inspect worker/cron thread configuration and cron last/next.
3. Classify process fault vs data residue vs true code defect.
4. Apply the smallest permanent fix that restores cron for **all** schedules.
5. Re-measure with runtime evidence.

Detailed narrative: [`case-studies/01-quality-scheduler-reliability.md`](../../case-studies/01-quality-scheduler-reliability.md).
