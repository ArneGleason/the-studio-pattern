# Instructions for AI Agents

Welcome to `<project-name>`.

This repository uses the Studio Pattern: one lead participant advances the project, another participant reviews or continues from a written handoff, and the project keeps lightweight memory surfaces so context survives across sessions.

Studio Pattern source:

- Version/date: `<YYYY-MM-DD or release>`
- Source repository: `the-studio-pattern`
- Source commit: `<commit-sha-or-date-if-no-commit>`
- License: `CC BY-SA 4.0`
- Local adaptation: `<brief note about project-specific changes>`

## Local Environment

- Agent/tool: `<agent-or-tool-name>`
- Machine handle: `<human-assigned-machine-handle>`
- Local checkout: `<absolute-path-if-useful>`
- Handle note: machine handles are human-assigned and should not be inferred from OS hostname without confirmation.

## First Reads

1. Read `README.md` for project purpose and normal commands.
2. Read `LOCAL_DEV_NOTES.md` for local workflow memory.
3. Read any project-specific pattern docs, if present.
4. Read `.agent/PROJECT_LOG.md` for recent decisions.
5. Read `.agent/REVIEW_QUEUE.md` for known risks and review focus.
6. If resuming or reviewing, read `.agent/session.json` and the latest handoff in `.agent/handoffs/` if one exists.

## Working Rules

- Prefer existing project patterns over new process.
- Keep changes scoped to the task.
- Update `LOCAL_DEV_NOTES.md` when you discover a useful command, port, setup step, or recurring gotcha.
- Update `.agent/PROJECT_LOG.md` when you make a meaningful implementation, product, research, or architecture decision.
- Update `.agent/REVIEW_QUEUE.md` when you leave a question, risk, or known weak spot for a reviewer.
- Keep `.agent/session.json` current before suspend, handoff, or model/environment transfer.
- Include machine handles in handoffs when work moves between physical machines or local environments.
- Write handoffs and review notes for the human owner first; another agent may be the next reader, but the human should be able to understand and route the work.
- If this project teaches a reusable Studio Pattern lesson, record it locally first, then send a cross-project feedback block to the canonical repository or thread.

## Validation

Before handoff or review, run the project's normal checks:

```sh
<project validation command>
```

Record any checks you could not run in the handoff.

## Handoff

When handing to another agent, reviewer, human, or future session:

1. Run validation where practical.
2. Update the memory files listed above.
3. Create or update a handoff under `.agent/handoffs/`.
4. Give the human owner a concise summary they can read and route.
5. Tell the next participant which files to read first.

## Project Safety

Add project-specific warnings here, especially around data loss, external services, credentials, generated assets, deployment, or irreversible actions.
