---
name: release-version-bump
description: Workflow command scaffold for release-version-bump in k8sgpt.
allowed_tools: ["Bash", "Read", "Write", "Grep", "Glob"]
---

# /release-version-bump

Use this workflow when working on **release-version-bump** in `k8sgpt`.

## Goal

Performs a release by updating the release manifest, changelog, and documentation.

## Common Files

- `.release-please-manifest.json`
- `CHANGELOG.md`
- `README.md`

## Suggested Sequence

1. Understand the current state and failure mode before editing.
2. Make the smallest coherent change that satisfies the workflow goal.
3. Run the most relevant verification for touched files.
4. Summarize what changed and what still needs review.

## Typical Commit Signals

- Update the release manifest file.
- Update the CHANGELOG.md with the new release notes.
- Update the README.md if necessary.

## Notes

- Treat this as a scaffold, not a hard-coded script.
- Update the command if the workflow evolves materially.