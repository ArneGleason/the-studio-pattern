# Review Queue

## Antigravity Review Follow-Up

Status: accepted and implemented in the self-hosting bootstrap pass.

Findings received 2026-05-09:

- P1: Dogfood the pattern in the canonical repository by adding root `AGENTS.md`, `LOCAL_DEV_NOTES.md`, and `.agent/` files.
- P2: Clarify whether high-churn project memory files such as `.agent/session.json` and `.agent/handoffs/` should be committed.

## Next Reviewer Focus

- Should `.agent/session.json` in adopting projects record both source commit and local adaptation commit?
- Do cross-project feedback blocks and traceability headers stay lightweight enough, or do they add ceremony outside genuinely cross-project situations?
- Antigravity sanity check: does `the-studio-pattern @ a6be02b` match the expected canonical shape and boundary model?

## Future Observation

- Watch whether committed `.agent/session.json` and `.agent/handoffs/` cause merge friction during concurrent meta-development. If they do, revisit whether public/highly collaborative repos need a different convention than private project repos.
