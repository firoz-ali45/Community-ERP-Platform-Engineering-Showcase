# 07 — Secure reporting boundaries

## Problem
PDFs and QWeb reports become an alternate query API.

## Observed symptom
Sensitive fields appear in prints for users who cannot open the form; cross-company data in exports.

## Forensic reasoning
Map report models, attachments, and controller routes against ACL expectations.

## Root cause / engineering challenge
Report development optimized for layout, not authorization.

## Minimal safe solution
Treat reports as security surfaces: company checks, group gates, and tests for forbidden fields.

## Validation method
Generate reports as low-privilege users; assert omissions and denials.

## Engineering lesson
Pretty output without authz is a vulnerability.

## Public-safe evidence
Checklist of report review questions.

## What remains private
Actual report templates and sample business PDFs.
