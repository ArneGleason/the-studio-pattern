# Roles

The Studio Pattern works best when each participant has a clear job and clear memory responsibilities.

## Human Owner

The human owner sets direction, taste, constraints, and acceptance criteria.

Responsibilities:

- Define what matters and why.
- Resolve tradeoffs that require taste or product judgment.
- Approve risky, destructive, externally visible, or expensive actions.
- Decide when local lessons should become canonical pattern updates.

## Lead Developer Agent

The lead developer agent advances the next coherent piece of work.

Responsibilities:

- Read the first-read path before changing the project.
- Implement or research within the current task boundary.
- Update `LOCAL_DEV_NOTES.md` when a command, port, setup step, or gotcha becomes reusable.
- Update `.agent/PROJECT_LOG.md` when a meaningful decision or direction change happens.
- Keep `.agent/session.json` current before suspend or handoff.
- Create a handoff when another model, reviewer, or future session needs to continue.

## Reviewer Agent

The reviewer agent examines the work from a separate perspective.

Responsibilities:

- Start from `AGENTS.md`, `LOCAL_DEV_NOTES.md`, `.agent/REVIEW_QUEUE.md`, the latest handoff, and relevant project docs.
- Prioritize bugs, data loss, missing tests, unclear assumptions, and memory gaps.
- File concrete findings with file and line references when possible.
- Review whether the project memory would let a future agent continue safely.

## Specialist Agent

A specialist agent handles a narrow task that benefits from a different model, tool, or skill.

Examples:

- security review,
- DSP or data analysis,
- UI polish,
- performance investigation,
- research synthesis,
- documentation pass.

Specialists should receive a tight brief and write their findings back into the same project memory surfaces instead of creating a separate shadow process.

## Human And Agent Handoffs

The pattern does not assume all handoffs are agent-to-agent. Human-to-agent, agent-to-human, and agent-to-future-self handoffs should use the same principle: write down the minimum context that prevents waste and mistakes.
