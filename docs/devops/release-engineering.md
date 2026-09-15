# Release engineering

## Immutable staging pattern

1. Build a release artifact from an exact commit.
2. Stage immutably under a release identity.
3. Atomically point the environment’s “current” pointer at that release.
4. Remount/restart only the intended environment service.
5. Verify runtime authority matches the promoted commit.

## Rollback

Retain prior release identities so rollback is a pointer move—not archaeology.
