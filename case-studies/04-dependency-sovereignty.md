# 04 — Dependency sovereignty

## Problem
Upstream Owl/CSS or module behavior breaks under “helpful” local edits to vendor trees, destroying reproducibility.

## Observed symptom
Environment-specific UI failures that cannot be reproduced from clean upstream pins.

## Forensic reasoning
Diff upstream pin vs running tree; detect silent edits and impure volume seeds.

## Root cause / engineering challenge
Treating vendored upstream as a writable workspace.

## Minimal safe solution
Pin upstream SHAs; keep trees pristine; implement fixes in first-party overlay/compat modules; gate digests in CI.

## Validation method
Hash/provenance checks; Sandbox proof on pristine seed; regression for the UI surface.

## Engineering lesson
Sovereignty is pins + overlays, not “we have a copy so we can edit it.”

## Public-safe evidence
Policy narrative; public upstream project links in NOTICE.

## What remains private
Full vendor mirrors, exact internal digests of customer deployments.
