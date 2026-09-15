# 11 — SSO boundary architecture

## Problem
Satellite applications need ERP identity without becoming a second ERP or a secret sprawl.

## Observed symptom
Duplicated user admin, unclear token audiences, or Hub/ERP coupling that breaks isolation.

## Forensic reasoning
Map issuer, audience, redirect, and subject namespace per environment; confirm secrets never enter Git.

## Root cause / engineering challenge
SSO treated as a convenience link rather than a cross-app trust boundary.

## Minimal safe solution
Explicit SSO contracts per environment; least-privilege scopes; separate Sandbox and Production identities; private secret stores.

## Validation method
Contract checks for expected issuer/audience patterns using non-secret config; negative tests for cross-environment token reuse.

## Engineering lesson
Boundaries are configuration and threat models—not a single shared password.

## Public-safe evidence
Abstract sequence diagram in prose.

## What remains private
Client secrets, real redirect URIs, implementation modules.
