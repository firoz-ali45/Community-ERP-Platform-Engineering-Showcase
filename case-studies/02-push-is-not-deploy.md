# 02 — Push is not deploy

## Problem
Teams equate “merged to the release branch” with “Sandbox updated,” breaking Management UAT trust.

## Observed symptom
Stakeholders see unexpected Sandbox changes after ordinary pushes, or engineers assume UAT already includes their commit.

## Forensic reasoning
Inspect control-plane triggers: does push mutate the environment, or is promotion a separate workflow with explicit inputs?

## Root cause / engineering challenge
Automatic deploy-on-push collapses review, UAT, and runtime identity into one irreversible step.

## Minimal safe solution
Option-style governance: Sandbox promotion only via manual, fail-closed dispatch against a named commit and reason; CI on PRs remains non-mutating.

## Validation method
Prove push does not remount Sandbox; prove dispatch updates runtime authority to the named commit only.

## Engineering lesson
Delivery speed without promotion discipline destroys UAT credibility.

## Public-safe evidence
Workflow-trigger matrix (push vs dispatch) described abstractly.

## What remains private
Real workflow files, secret names tied to infrastructure, host access methods.
