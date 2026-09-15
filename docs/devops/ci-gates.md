# CI gates

## Purpose

Gates encode non-negotiable properties: governance integrity, dependency pin honesty, workflow safety shape, and static self-tests.

## Principles

1. Fail closed on missing authority markers.
2. Do not “fix” a gate by deleting it.
3. Separate runner-static checks from live environment mutation.
4. Keep Production-oriented deploy workflows out of Sandbox pipelines.

## Public note

Exact workflow files for private infrastructure are not published here. This document describes intent and review criteria only.
