# Pattern Overview

The Studio Pattern is a coordination method for projects where humans and multiple AI agents work together over time.

It assumes the hard part is not only generating work. The hard part is preserving enough context that the next session, model, or reviewer can move with judgment instead of rediscovering the same facts.

## The Loop

1. Orient from a short, known reading path.
2. Do one coherent piece of work.
3. Record decisions, commands, and risks where future agents will look.
4. Prepare a concise, human-readable handoff when changing agents, environments, or sessions.
5. Let the human owner read the handoff, add judgment or course correction, and decide how to route the next step.
6. Review from a separate perspective.
7. Promote useful lessons back into the local project and, when reusable, this repository.

## Human-Mediated Relay

The Studio Pattern assumes a human remains in the loop as context steward, not only as final approver.

When work moves between agents or environments, the human should be able to read the summary, understand what changed, add missing context, and decide whether the next step still matches the project's goals. This is why handoffs should be written for human comprehension first.

Direct agent-to-agent transfer can be useful when the human explicitly delegates it, but the default pattern should preserve human visibility. The relay moment is where taste, intent, risk tolerance, and opportunity recognition enter the system.

## Distributed Local Environments

The Studio Pattern works especially well when different agents run in different local environments. Physical or machine-level separation makes the system more robust: one machine can fail, drift, or be rebuilt without destroying every participant's working context.

Distinguish three identities:

- **Human:** the stakeholder or relay person making routing decisions.
- **Agent/tool:** the interface or model doing the work, such as Codex or Antigravity.
- **Machine handle:** the human-assigned name for the physical machine or local environment where that agent is running.

Use machine handles when a handoff depends on local checkout state, installed tools, credentials, hardware, or physical redundancy. Do not treat an OS hostname as authoritative unless the human owner explicitly maps it to a Studio Pattern handle.

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
