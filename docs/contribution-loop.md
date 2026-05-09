# Contribution Loop

The Studio Pattern improves when project-specific lessons become reusable pattern changes.

Each adopting project is a field test.

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
canonical pattern -> project adaptation -> field use -> local lesson -> reusable refinement -> canonical pattern
```

The loop should stay porous. Projects should be free to adapt locally, and the canonical pattern should only absorb what remains broadly useful.
