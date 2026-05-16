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
2. Check `git status --short`, inspect the intended diff scope, and remove unrelated local dev artifacts, generated files, local databases, OS metadata, raw logs, and trailing whitespace from the handoff diff.
3. Update `LOCAL_DEV_NOTES.md` if a reusable command or gotcha was discovered.
4. Update `.agent/PROJECT_LOG.md` if a durable decision was made.
5. Update `.agent/REVIEW_QUEUE.md` if there are known risks or questions.
6. Update `.agent/session.json`.
7. Write a timestamped handoff note under `.agent/handoffs/` when the project uses handoff files.

If unrelated or noisy files must remain in the diff, call them out explicitly and explain why they are in scope. For review handoffs, do not merely note avoidable noise; clean it before asking the reviewer to reason about the change.

## Handoff Contents

A good handoff includes:

- task name,
- timestamp,
- branch and commit when available,
- status,
- requested role and allowed action boundary,
- review target when the handoff asks for review,
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

## Role And Action Boundary

When handing work to another participant, say what role they are being asked to play.

Useful examples:

- `Role requested: Lead developer`
- `Role requested: Reviewer`
- `Role requested: Specialist`
- `Allowed actions: static review and smoke test only`
- `Disallowed actions: no code edits, commits, pushes, or product-scope changes`

This boundary is especially important when two agents are collaborating through a human relay. It prevents a reviewer from becoming an accidental implementer and helps the human owner compare feedback from separate perspectives.

## Review Target And Iteration Hygiene

When a handoff asks for code or artifact review, include the exact target:

```md
## Review Target

- Repo: `<repo>`
- Branch: `<branch>`
- Commit: `<commit>`
- Base: `<base branch or commit>`
- PR or compare URL: `<url or none>`
- Requirements source: `<file, directory, issue, or handoff>`
- Local checkout status: `<known clean, dirty, not available, or unknown>`
```

For review iterations, prefer PR-centric updates. The original handoff can act like a PR description: keep it accurate enough for orientation, then use new commit SHAs and short pass-back messages for each review cycle. Do not rewrite the whole handoff for every small fix unless the architecture, scope, or acceptance criteria changed.

Before asking for review, clean up the branch enough that the reviewer can focus on product and code risks:

- run the project validation commands when practical,
- run whitespace or formatting checks such as `git diff --check`,
- inspect `git status --short`,
- inspect `git diff --stat <base>...<branch>` or the project equivalent,
- remove generated artifacts, local databases, OS metadata, raw logs, and unrelated files,
- record exact build, lint, and test commands, including special flags or dependency quirks,
- mark stale handoff claims as superseded instead of leaving contradictory summaries in the message.

If checks cannot run because of local dependencies, credentials, network access, or machine state, say that directly. The environment finding may belong in `LOCAL_DEV_NOTES.md`; the handoff should still tell the reviewer what happened.

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
- Role requested: <lead developer | reviewer | specialist | future session>
- Allowed actions: <implementation | static review | smoke test | docs update | etc.>
- Disallowed actions: <optional boundaries>

## Review Target

- Repo: <repo>
- Branch: <branch>
- Commit: <commit>
- Base: <base branch or commit>
- PR or compare URL: <url-or-none>
- Requirements source: <file, directory, issue, or handoff>
- Local checkout status: <known-clean | dirty | unavailable | unknown>

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
