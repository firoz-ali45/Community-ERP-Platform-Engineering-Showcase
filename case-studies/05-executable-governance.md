# 05 — Executable governance

## Problem
Policy PDFs do not stop agents or humans from weakening security or skipping UAT.

## Observed symptom
“Temporary” ACL looseness, missing branch targets, or Production-tinted actions during Sandbox work.

## Forensic reasoning
Ask whether controls are enforced in CI/preflight, or merely documented.

## Root cause / engineering challenge
Governance as prose without executable stops.

## Minimal safe solution
Layered precedence with automated gates and hard-stop phrases for forbidden classes of change.

## Validation method
Gate self-tests; adversarial fixtures that must fail; audit that deploy workflows remain Sandbox-scoped.

## Engineering lesson
If an agent can shrug it off, it is not governance.

## Public-safe evidence
Abstract precedence table (no passcodes).

## What remains private
Unseal phrases, Owner authorization rituals, private constitution JSON.
