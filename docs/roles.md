# Roles

The Studio Pattern works best when each participant has a clear job and clear memory responsibilities.

## Human Owner

The human owner sets direction, taste, constraints, and acceptance criteria.

Responsibilities:

- Define what matters and why.
- Resolve tradeoffs that require taste or product judgment.
- Approve risky, destructive, externally visible, or expensive actions.
- Read cross-agent handoffs closely enough to understand the current state.
- Add missing context, course corrections, or opportunity notes before passing work onward.
- Decide which agent, model, environment, or human should receive the next handoff.
- Choose participant roles and model/tool diversity intentionally when it can improve judgment, coverage, or implementation quality.
- Decide when direct agent-to-agent or automated orchestration is allowed.
- Decide when local lessons should become canonical pattern updates.

## Human Context Steward

In many projects, the human owner also acts as the context steward.

This is an active role, not a mailbox. The context steward carries summaries between agents, reads what is being passed, checks whether the work still matches the project intent, and adds judgment before the next participant acts.

The goal is not to slow the work down. The goal is to keep the human stakeholder oriented enough to notice drift, redirect effort, recognize new opportunities, and understand what has been built so far.

The relay work can look like clerical copying from the outside, but it is a form of active participation. Reading each pass-back as it happens lets the human learn the project over time, adjust the direction between cycles, and experience the work as an unfolding story rather than a final summary. That ongoing engagement is part of the value of the pattern.

The context steward may deliberately keep agents separated by a human-readable message boundary. This helps preserve independent perspectives while still giving the human owner a chance to annotate, correct, or stop the loop before the next participant acts.

That separation is especially useful when different models are chosen to cover different strengths and blind spots. The context steward does not only move text between tools; they decide whether the next perspective should be a builder, reviewer, specialist, future session, or canonical-pattern contributor.

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

When choosing a specialist, name the reason for the specialization. Examples: different model assumptions, a stronger research tool, a local environment with required assets, or a domain-specific workflow.

## Human And Agent Handoffs

The pattern does not assume all handoffs are agent-to-agent. Human-to-agent, agent-to-human, and agent-to-future-self handoffs should use the same principle: write down the minimum context that prevents waste and mistakes.

By default, write handoffs as if the human owner will read them before they reach the next agent. If a project intentionally uses direct agent-to-agent relay, keep a human-readable summary in the project memory so the human can regain context quickly.
