# UAT protection

## Intent

During Management UAT, Sandbox is a protected evaluation surface. Engineering urgency must not silently rewrite what stakeholders are validating.

## Patterns

- Disable automatic environment mutation on ordinary git push.
- Require explicit promotion inputs (commit identity + reason).
- Separate “CI passed” from “UAT environment updated.”
- Prefer read-only diagnostics while investigating incidents.

## Anti-pattern

Hotfixing Sandbox via ad-hoc remote file copy outside the governed promote path.
