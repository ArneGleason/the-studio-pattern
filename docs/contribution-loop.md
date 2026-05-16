# Contribution Loop

The Studio Pattern improves when project-specific lessons become reusable pattern changes.

Each adopting project is a field test.

## Project Boundaries

Keep the canonical pattern and adopting projects distinct.

- The canonical repository owns shared templates, protocols, docs, case studies, and meta-process decisions.
- An adopting project owns its product work, research work, local commands, local `.agent/` files, and project-specific adaptations.
- A project thread should not become the only place where canonical pattern changes are decided.
- A canonical thread should not take over an adopting project's local implementation details unless they are evidence for a reusable pattern change.

When an adopting project teaches something reusable, record the local evidence in that project first. Then bring a concise cross-project feedback block back to the canonical Studio Pattern repo or thread.

## Local First

When a project discovers something useful, record it locally before changing the canonical repo.

Good local evidence includes:

- a handoff that worked,
- a review finding caused by missing memory,
- a command that agents repeatedly rediscovered,
- a suspend/resume failure,
- a local adaptation that made the next session faster,
- a stale instruction that caused a mistake.

## Decide Scope

Ask:

- Is this only true for one project?
- Is this true for a class of projects?
- Does this change a template?
- Does this change a protocol?
- Is it still a hypothesis that belongs in `revelations.md`?

## Promote Back

Reusable lessons can become:

- a docs update,
- a template update,
- a new case-study note,
- a changelog entry,
- a revelation or working hypothesis,
- a future script or utility, if the need repeats.

## Mid-Project Retrospectives

Do not wait until the end of a project to capture pattern feedback. Mid-project retrospectives are useful when the participants can still remember what helped, what hurt, and which parts of the relay changed the work.

For a multi-agent project, ask for three perspectives when practical:

- the human context steward,
- the lead developer agent,
- the reviewer or specialist agent.

The human perspective is not just a final approval signal. The human may be learning the project through the rhythm of handoffs, noticing product drift between cycles, and deciding which variations in agent behavior should be encouraged or discouraged. Capture that experience directly.

Keep mid-project retrospectives provisional. Record them as field evidence first, then decide whether each lesson belongs in:

- a case-study note,
- `revelations.md`,
- a protocol update,
- a template update,
- a project-specific `LOCAL_DEV_NOTES.md` entry.

Useful prompts:

- What worked well?
- What caused friction or stale context?
- What should become a canonical pattern change?
- What should remain project-specific?
- What practice will each participant adopt immediately?

## Cross-Project Feedback Blocks

Use a cross-project feedback block when a lesson, review result, or boundary clarification moves from one project to another.

A copyable workflow template lives at `templates/.agent/workflows/cross-project-feedback.md`.

The traceability header makes the origin clear without adding process to ordinary local notes:

```md
# Cross-Project Feedback

- To: `the-studio-pattern`
- From: `<person, agent, source project, or source thread>`
- To agent: `<agent or tool, if relevant>`
- To machine: `<machine-handle, if relevant>`
- From agent: `<agent or tool, if relevant>`
- From machine: `<machine-handle, if relevant>`
- Created: `<YYYY-MM-DD>`
- Origin: `<source repo, commit, review, handoff, or session>`
- Subject: `<short subject>`

## Context

<why this is crossing project boundaries>

## Local Evidence

- `<verified file, commit, review finding, or workflow observation>`

## Reusable Question

<what the canonical pattern should consider>

## Proposed Canonical Change

<smallest reusable docs, template, or protocol change>

## Boundary Note

<what remains local to the source project>
```

Do not require this block for every local decision. Use it when the destination project would otherwise lose track of where the idea came from.

## Keep Canonical Changes Evidence-Based

When proposing a change, include:

- the source project,
- the observed problem,
- the local fix,
- why it should be canonical,
- any tradeoff or risk.

## Avoid Premature Process

Do not promote a project-specific ritual just because it feels tidy. Promote it when it prevents repeated confusion, catches real risks, or makes handoff measurably easier.

## Expected Flow

```txt
canonical pattern -> project adaptation -> field use -> local lesson -> cross-project feedback -> reusable refinement -> canonical pattern
```

The loop should stay porous. Projects should be free to adapt locally, and the canonical pattern should only absorb what remains broadly useful.
