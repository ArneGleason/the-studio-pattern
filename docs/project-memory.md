# Project Memory

Project memory is the practical context a future human or agent needs to continue work without replaying the whole history.

Keep it small, current, and close to the repository.

## Memory Surfaces

### `AGENTS.md`

Fast orientation for a new agent.

Should include:

- what the project is,
- the first-read order,
- important commands,
- local Studio Pattern version/date/commit,
- project-specific working rules,
- where review and handoff context lives.

### `LOCAL_DEV_NOTES.md`

Living local workflow memory.

Should include:

- commands,
- ports and URLs,
- setup gotchas,
- deployment or tunnel notes,
- recurring validation steps,
- operational warnings.

Update this whenever someone figures out a detail that future work would otherwise rediscover.

### `.agent/PROJECT_LOG.md`

Chronological record of meaningful project events and decisions.

Good entries are short. Record what changed, why it matters, and any follow-up created.

### `.agent/REVIEW_QUEUE.md`

Focused queue for reviewer attention.

Use it for:

- known weak spots,
- open questions,
- risky assumptions,
- missing tests,
- areas where fresh eyes are needed.

### `.agent/session.json`

Machine-readable latest state.

Useful fields:

- project,
- pattern source version/date/commit,
- current lead,
- intended reviewer,
- branch,
- commit,
- last task,
- status,
- updated timestamp,
- last handoff path,
- project-specific state summary.

### `.agent/handoffs/`

Timestamped handoff notes.

Use handoffs when work crosses sessions, models, environments, reviewers, or meaningful task boundaries.

### `.agent/workflows/`

Short workflow recipes for recurring actions such as resume, suspend, deploy, review, or release.

Workflows should be executable reading aids: a future agent should know what to run and what to read next.

## What Belongs Where

- Commands and local setup belong in `LOCAL_DEV_NOTES.md`.
- Durable decisions belong in `.agent/PROJECT_LOG.md`.
- Reviewer questions belong in `.agent/REVIEW_QUEUE.md`.
- Latest resumable state belongs in `.agent/session.json`.
- Cross-agent context belongs in `.agent/handoffs/`.
- Canonical reusable method belongs in this repository.

## Keep Memory Honest

Delete or revise stale instructions. A wrong memory surface is worse than a missing one because agents will trust it under time pressure.
