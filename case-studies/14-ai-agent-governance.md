# 14 — AI agent governance

## Problem
Agents can ship irreversible ERP risk faster than humans can review.

## Observed symptom
Wrong-branch edits, speculative refactors in tax/HR modules, secret-bearing debug output.

## Forensic reasoning
Evaluate whether agent tooling has executable stops (branch, freeze, domain auth) or only polite prompts.

## Root cause / engineering challenge
Treating agents as senior architects without control-plane constraints.

## Minimal safe solution
Hard stops, freezes, domain allowlists, read-only default for incidents, ban on invented Production proof.

## Validation method
Adversarial prompt suites against governance evaluators; CI that fails on forbidden workflow shapes.

## Engineering lesson
Autonomy without brakes is an outage generator.

## Public-safe evidence
Policy themes in docs/governance.

## What remains private
Private agent rulesets and passcodes.
