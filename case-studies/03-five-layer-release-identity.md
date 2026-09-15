# 03 — Five-layer release identity

## Problem
Debates about “what is live” devolve into screenshots and chat messages.

## Observed symptom
Source tip, promoted release, and runtime disagree—or nobody can prove agreement.

## Forensic reasoning
Separate Git identity from environment authority records and mount proofs.

## Root cause / engineering challenge
Missing or ignored runtime authority artifact after promotion.

## Minimal safe solution
Require an environment-side authority record for every promote; verify it in post-promote smoke.

## Validation method
Compare commit, promoted identity, and runtime authority fields; HTTP/login smoke on the intended environment only.

## Engineering lesson
Without layer five, layers one through four are storytelling.

## Public-safe evidence
Synthetic JSON example in `examples/`.

## What remains private
Real authority JSON from live systems; mount source strings.
