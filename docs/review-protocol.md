# Review Protocol

Review is a separate perspective, not a ceremonial rubber stamp.

The reviewer should look for defects, weak assumptions, data-loss risks, missing tests, unclear project memory, and places where the next agent would get lost.

## Reviewer Starting Path

1. Read `AGENTS.md`.
2. Read `LOCAL_DEV_NOTES.md`.
3. Read `.agent/REVIEW_QUEUE.md`.
4. Read the latest handoff in `.agent/handoffs/` if present.
5. Read `.agent/PROJECT_LOG.md` for recent decisions.
6. Inspect the changed code or artifacts.
7. Run the checks named by the project when practical.

## What To Review

- correctness,
- safety and data loss,
- missing validation,
- unclear assumptions,
- insufficient tests,
- awkward workflows,
- stale or missing memory surfaces,
- failure to update docs after important changes.

## Finding Format

Prefer concrete findings:

```md
## Findings

- [P1] <brief title>
  - File: <path>:<line>
  - Problem: <what can go wrong>
  - Suggested fix: <smallest useful fix>
```

Use severity only to help ordering:

- `P0`: blocks use or can cause severe loss.
- `P1`: likely bug or serious workflow risk.
- `P2`: important but not blocking.
- `P3`: polish or future improvement.

## Review The Memory

A Studio Pattern review should ask:

- Could a new agent find the right first reads?
- Are commands and ports recorded?
- Are decisions visible?
- Are open questions in the review queue?
- Is the latest session state accurate?
- Does the handoff say what was and was not checked?

If the answer is no, that is a valid review finding.
