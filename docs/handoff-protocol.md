# Handoff Protocol

A handoff is a compact transfer of project state. It should let another human or agent continue with fewer false starts.

Use a handoff when:

- switching from lead developer to reviewer,
- pausing work for a later session,
- changing model or environment,
- ending a coherent task,
- leaving behind state that is not obvious from the code.

## Before Handoff

1. Run the project's normal validation checks.
2. Check git status and note uncommitted work.
3. Update `LOCAL_DEV_NOTES.md` if a reusable command or gotcha was discovered.
4. Update `.agent/PROJECT_LOG.md` if a durable decision was made.
5. Update `.agent/REVIEW_QUEUE.md` if there are known risks or questions.
6. Update `.agent/session.json`.
7. Write a timestamped handoff note under `.agent/handoffs/` when the project uses handoff files.

## Handoff Contents

A good handoff includes:

- task name,
- timestamp,
- branch and commit when available,
- status,
- what changed,
- current repo state,
- checks run,
- checks not run,
- reviewer starting points,
- open questions,
- project-specific state summary.

Keep the handoff concise. Link to memory surfaces rather than copying long histories.

## Suspend Versus Handoff

Suspend means the same lead or project owner may resume later.

Handoff means another participant should be able to continue or review.

Many projects can use the same mechanism for both, but the intent should be clear in `status` or the handoff title.

## Example Handoff Skeleton

~~~md
# Studio Handoff: <task>

- Timestamp: <iso-timestamp>
- Status: handoff | suspended
- Branch: <branch>
- Commit: <commit-or-none>
- Studio Pattern: <date-or-version> from <commit>

## What Changed

- ...

## Current Repo State

```txt
<git status --short>
```

## Checks

- Passed: ...
- Not run: ...

## Reviewer Starting Points

- `AGENTS.md`
- `LOCAL_DEV_NOTES.md`
- `.agent/REVIEW_QUEUE.md`
- `<latest relevant docs>`

## Open Questions

- ...
~~~
