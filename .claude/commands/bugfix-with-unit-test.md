---
name: bugfix-with-unit-test
description: Workflow command scaffold for bugfix-with-unit-test in k8sgpt.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /bugfix-with-unit-test

Use this workflow when working on **bugfix-with-unit-test** in `k8sgpt`.

## Goal

Fixes a bug in an analyzer and adds or updates a unit test to cover the regression or new code path.

## Common Files

- `pkg/analyzer/*.go`
- `pkg/analyzer/*_test.go`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Identify and fix the bug in the analyzer implementation file (e.g., *.go).
- Add or update a corresponding unit test file (e.g., *_test.go) to cover the bug or regression.
- Commit both the implementation and test changes together.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.