# Review Queue

## Antigravity Review Follow-Up

Status: accepted and implemented in the self-hosting bootstrap pass.

Findings received 2026-05-09:

- P1: Dogfood the pattern in the canonical repository by adding root `AGENTS.md`, `LOCAL_DEV_NOTES.md`, and `.agent/` files.
- P2: Clarify whether high-churn project memory files such as `.agent/session.json` and `.agent/handoffs/` should be committed.

## Next Reviewer Focus

- Does the self-hosting root memory duplicate the templates too much, or does it clarify the canonical repo's own work?
- Is the version-control guidance clear enough for both public docs repos and private application repos?
- Should the canonical repo provide a small adoption script, or is copy/adapt still the right first move?
- Should `.agent/session.json` in adopting projects record both source commit and local adaptation commit?
