# Task 24 — Final acceptance and launch

## Objective
Run the complete release checklist, load approved content, and launch only approved features.

## Dependencies
- All prior tasks approved, unless an approved task amendment says otherwise.
- Relevant open items in `docs/09_DECISIONS_AND_OPEN_ITEMS.md` resolved or explicitly feature-flagged.

## In scope
- Regression
- real-device/browser checks
- content/legal/provider gates
- production smoke
- monitoring
- rollback readiness
- owner sign-off

## Non-goals
- No launch with critical blocker
- No enabling unverified providers/features

## Required implementation behavior
- Inspect the existing repository before changing files.
- Create/update `.agent/active-plan.md`.
- Follow `AGENTS.md` architecture, security, privacy, accessibility, and quality rules.
- Add/update appropriate automated tests.
- Do not weaken earlier acceptance criteria.
- Update affected documentation and ADRs.
- Keep unconfigured or unapproved external features disabled.

## Acceptance criteria
- All launch gates documented
- owner explicitly accepts limitations
- feature flags match readiness
- post-launch checks pass
- rollback available

## Validation
- Full automated suite
- browser critical paths
- production smoke checks
- Run every applicable command documented in `AGENTS.md`.
- Record exact results and any environment limitations.

## Completion report
Use the 12-part completion report in `AGENTS.md`.

## Stop point
End with a final release report and wait for explicit owner launch approval.

End exactly:

`TASK COMPLETE — AWAITING REVIEW`
