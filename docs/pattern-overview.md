# Pattern Overview

The Studio Pattern is a coordination method for projects where humans and multiple AI agents work together over time.

It assumes the hard part is not only generating work. The hard part is preserving enough context that the next session, model, or reviewer can move with judgment instead of rediscovering the same facts.

## The Loop

1. Orient from a short, known reading path.
2. Do one coherent piece of work.
3. Record decisions, commands, and risks where future agents will look.
4. Prepare a concise handoff when changing agents, environments, or sessions.
5. Review from a separate perspective.
6. Promote useful lessons back into the local project and, when reusable, this repository.

## The Minimum Viable Pattern

A project can use the pattern with only:

- `AGENTS.md`
- `LOCAL_DEV_NOTES.md`
- `.agent/PROJECT_LOG.md`
- `.agent/REVIEW_QUEUE.md`
- `.agent/session.json`
- `.agent/workflows/resume.md`
- `.agent/workflows/suspend.md`

Projects with more complicated state can add generated handoffs, scripts, backups, or richer logs, but those should serve a real workflow.

## What The Pattern Is For

- Preserving context across sessions.
- Coordinating a lead developer agent and reviewer agent.
- Making handoffs explicit between models, tools, machines, or environments.
- Recording durable decisions and lessons learned.
- Helping project-specific improvements flow back into a canonical pattern.

## What The Pattern Is Not

- It is not a full project-management system.
- It is not a multi-agent orchestration platform.
- It is not a replacement for tests, commits, issues, or human judgment.
- It is not meant to force every project into identical files beyond a small shared memory surface.

## Evidence Bias

Changes to the canonical pattern should be grounded in field evidence:

- a repeated failure,
- a successful handoff,
- a review finding that exposed missing memory,
- a command or setup note that saved future work,
- a local adaptation that proved useful outside its original project.
