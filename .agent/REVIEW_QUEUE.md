# Review Queue

## Antigravity Review Follow-Up

Status: accepted and implemented in the self-hosting bootstrap pass.

Findings received 2026-05-09:

- P1: Dogfood the pattern in the canonical repository by adding root `AGENTS.md`, `LOCAL_DEV_NOTES.md`, and `.agent/` files.
- P2: Clarify whether high-churn project memory files such as `.agent/session.json` and `.agent/handoffs/` should be committed.

## Next Reviewer Focus

- Should `.agent/session.json` in adopting projects record both source commit and local adaptation commit?

## 2026-05-11 Review Follow-Up

Status: accepted and implemented in the Warehouse retrospective docs pass.

- Antigravity confirmed the role/action boundary and human context-steward language were well balanced.
- Accepted finding: `Before Handoff` was too soft when it said to note uncommitted work; tightened it to require removing avoidable local artifacts and whitespace from the review diff.
- Accepted finding: Warehouse's `session_manager.js` should be clearly marked as a project-specific suspend/resume example, not canonical doctrine.

## Future Observation

- Watch whether committed `.agent/session.json` and `.agent/handoffs/` cause merge friction during concurrent meta-development. If they do, revisit whether public/highly collaborative repos need a different convention than private project repos.
- Consider whether adopting projects would benefit from a tiny `.gitignore` starter snippet for sensitive/local-only/large/volatile files. Keep project-specific for now to avoid premature process.
