# AI / agent governance

## Problem

Autonomous coding agents can bypass human caution: wrong branch, weakened security, speculative business-logic edits, or secret leakage into logs.

## Control patterns

- Explicit branch targeting for writes
- Freezes that block application asset edits without unseal authority
- Hard stops for Production destructive actions
- Domain authorization for tax, HR, inventory regulation, and auth
- Preference for read-only audits when evidence is missing
- Ban on inventing runtime proof from Sandbox alone when Production is claimed

## Public lesson

Agents are powerful juniors with root access unless governance is executable.
