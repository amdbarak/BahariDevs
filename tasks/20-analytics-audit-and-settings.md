# Task 20 — Analytics, audit viewer, and settings

## Objective
Implement privacy-conscious operational analytics, audit review, and safe settings.

## Dependencies
- All prior tasks approved, unless an approved task amendment says otherwise.
- Relevant open items in `docs/09_DECISIONS_AND_OPEN_ITEMS.md` resolved or explicitly feature-flagged.

## In scope
- Request volume/outcomes
- workload
- service distribution
- lead source where consented
- audit filters
- provider/status settings
- feature flags

## Non-goals
- No invasive tracking
- No secret values displayed back

## Required implementation behavior
- Inspect the existing repository before changing files.
- Create/update `.agent/active-plan.md`.
- Follow `AGENTS.md` architecture, security, privacy, accessibility, and quality rules.
- Add/update appropriate automated tests.
- Do not weaken earlier acceptance criteria.
- Update affected documentation and ADRs.
- Keep unconfigured or unapproved external features disabled.

## Acceptance criteria
- Metrics are defined and reproducible
- audit immutable to normal admins
- settings validated/encrypted where needed
- secret fields are write-only/masked

## Validation
- Metric query tests
- audit authorization tests
- settings validation tests
- Run every applicable command documented in `AGENTS.md`.
- Record exact results and any environment limitations.

## Completion report
Use the 12-part completion report in `AGENTS.md`.

## Stop point
Stop after data accuracy review.

End exactly:

`TASK COMPLETE — AWAITING REVIEW`
