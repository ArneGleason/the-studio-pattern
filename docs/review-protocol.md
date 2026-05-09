# Review Protocol

Review is a separate perspective, not a ceremonial rubber stamp.

The reviewer should look for defects, weak assumptions, data-loss risks, missing tests, unclear project memory, and places where the next agent would get lost.

When a review crosses project boundaries, state the boundary explicitly. For example, reviewing an adopting project's local Studio Pattern files is different from changing the canonical pattern itself.

Reviews should be written so the human owner can understand and route them. The reviewer is not only speaking to the lead agent; they are helping the human decide whether to accept, redirect, deepen, or pause the work.

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
- handoffs or reviews that are too opaque for the human owner to route intelligently.

## Cross-Project Reviews

If a review finding from an adopting project may change the canonical pattern, separate the local finding from the reusable lesson.

Use a traceability header when sending that lesson to another project or thread:

```md
- To: `the-studio-pattern`
- From: `<source project or reviewer>`
- To agent: `<agent or tool, if relevant>`
- To machine: `<machine-handle, if relevant>`
- From agent: `<agent or tool, if relevant>`
- From machine: `<machine-handle, if relevant>`
- Created: `<YYYY-MM-DD>`
- Origin: `<review, handoff, issue, commit, or thread>`
- Subject: `<short subject>`
```

Then include:

- the local evidence,
- the project-specific fix, if any,
- the reusable question for the canonical pattern,
- what should remain local to the source project.

## Environment Awareness

When reviewing across machines, include the agent/tool and machine handle in the review context. This helps distinguish model behavior from local environment behavior.

Ask:

- Which machine produced the work?
- Which machine is reviewing it?
- Are the local checkouts at the same commit?
- Could a finding be caused by dependencies, credentials, caches, hardware, or local-only files?

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
- Could the human owner understand the review well enough to make the next routing decision?
- Are commands and ports recorded?
- Are decisions visible?
- Are open questions in the review queue?
- Is the latest session state accurate?
- Does the handoff say what was and was not checked?

If the answer is no, that is a valid review finding.
