# Task 16 — Quotations and acceptance

## Objective
Implement versioned quotes connected to requests and service items.

## Dependencies
- All prior tasks approved, unless an approved task amendment says otherwise.
- Relevant open items in `docs/09_DECISIONS_AND_OPEN_ITEMS.md` resolved or explicitly feature-flagged.

## In scope
- Draft/version/send/accept/decline/expire/supersede
- line items
- currency
- validity
- secure guest view/acceptance challenge
- PDF/export

## Non-goals
- No online payment
- No assumed tax rate

## Required implementation behavior
- Inspect the existing repository before changing files.
- Create/update `.agent/active-plan.md`.
- Follow `AGENTS.md` architecture, security, privacy, accessibility, and quality rules.
- Add/update appropriate automated tests.
- Do not weaken earlier acceptance criteria.
- Update affected documentation and ADRs.
- Keep unconfigured or unapproved external features disabled.

## Acceptance criteria
- Issued version immutable
- acceptance identity/time captured
- totals use safe money handling
- expired quote cannot be accepted
- sensitive access verified

## Validation
- Money/version tests
- authorization tests
- acceptance tests
- PDF smoke test
- Run every applicable command documented in `AGENTS.md`.
- Record exact results and any environment limitations.

## Completion report
Use the 12-part completion report in `AGENTS.md`.

## Stop point
Stop after commercial review.

End exactly:

`TASK COMPLETE — AWAITING REVIEW`
