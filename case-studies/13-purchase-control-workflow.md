# 13 — Purchase control workflow

## Problem
Uncontrolled purchasing creates financial and inventory leakage.

## Observed symptom
Orders bypass requisition/approval expectations; weak audit trails.

## Forensic reasoning
Map document states, approvers, and company scoping from requisition to PO to receipt.

## Root cause / engineering challenge
Purchase treated as clerical entry rather than a controlled pipeline.

## Minimal safe solution
Explicit requisition/approval models, access rights, and tests for forbidden transitions.

## Validation method
State-machine tests; negative permission tests across companies.

## Engineering lesson
Controls belong in workflow + security, not in tribal email approval.

## Public-safe evidence
Abstract state list (draft → submitted → approved → ordered).

## What remains private
Module source and real approval matrices.
