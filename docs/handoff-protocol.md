# Handoff Protocol

A handoff is a compact transfer of project state. It should let the human owner understand the state of the work and let another human or agent continue with fewer false starts.

Use a handoff when:

- switching from lead developer to reviewer,
- pausing work for a later session,
- changing model or environment,
- moving context between projects or project threads,
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
- traceability header when the handoff crosses projects or threads,
- agent and machine handles when local environment identity matters,
- what changed,
- what the human owner should understand before passing it on,
- current repo state,
- checks run,
- checks not run,
- reviewer starting points,
- open questions,
- project-specific state summary.

Keep the handoff concise. Link to memory surfaces rather than copying long histories.

## Human-Mediated Handoff

Write handoffs for human comprehension first.

The human owner should be able to read the handoff, understand what changed, decide whether the work still matches their goals, and add context before routing it to a reviewer, specialist, future session, or different environment.

This human relay is part of the pattern. It keeps the stakeholder oriented and creates a natural checkpoint for course correction, priority changes, and noticing useful opportunities.

If a project intentionally uses direct agent-to-agent handoff, still leave a human-readable summary in `.agent/handoffs/` or `.agent/session.json`.

## Traceability Header

Use a traceability header when a handoff, review note, or feedback block crosses project, repo, or thread boundaries.

Recommended fields:

```md
- To: `<destination project or thread>`
- From: `<person, agent, source project, or source thread>`
- Created: `<YYYY-MM-DD>`
- Origin: `<source repo, commit, review, handoff, or session>`
- Subject: `<short subject>`
```

Do not require this header for ordinary local suspend/resume notes. Use it when the reader may not otherwise know which project owns the next action.

## Machine Handles

Use a machine handle when the physical machine or local environment matters to the handoff.

The agent/tool name and machine handle are different:

- Agent/tool: `Codex`, `Antigravity`, `Claude`, or another development environment.
- Machine handle: `macbook-pro-m5`, `mac-mini-pro-m4`, `pc-workstation`, or another human-assigned environment name.

Machine handles should be:

- stable across sessions,
- human-readable,
- lowercase kebab-case by default,
- assigned or confirmed by the human owner,
- independent of OS hostname, serial number, username, or network name.

Do not auto-infer a canonical handle from the current machine name. A project may record a non-authoritative OS hostname for troubleshooting, but the human-assigned handle is what belongs in handoffs.

When useful, extend the traceability header:

```md
- To agent: `<agent or tool>`
- To machine: `<machine-handle>`
- From agent: `<agent or tool>`
- From machine: `<machine-handle>`
```

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

<!-- If this crosses projects or threads, add:
- To: <destination>
- From: <source>
- Created: <YYYY-MM-DD>
- Origin: <source context>
- Subject: <short subject>
-->

<!-- If local environments matter, add:
- To agent: <agent or tool>
- To machine: <machine-handle>
- From agent: <agent or tool>
- From machine: <machine-handle>
-->

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
