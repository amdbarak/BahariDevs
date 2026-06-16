# Task 09 — Guest request intake and secure tracking

## Objective
Implement secure multi-service guest submission and tokenized tracking access.

## Dependencies
- All prior tasks approved, unless an approved task amendment says otherwise.
- Relevant open items in `docs/09_DECISIONS_AND_OPEN_ITEMS.md` resolved or explicitly feature-flagged.

## In scope
- Multi-step form
- idempotency
- business number
- token issue/hash/revoke
- contact/location/services/priority/date
- consent
- confirmation
- safe tracking shell

## Non-goals
- No full workflow UI
- No client accounts

## Required implementation behavior
- Inspect the existing repository before changing files.
- Create/update `.agent/active-plan.md`.
- Follow `AGENTS.md` architecture, security, privacy, accessibility, and quality rules.
- Add/update appropriate automated tests.
- Do not weaken earlier acceptance criteria.
- Update affected documentation and ADRs.
- Keep unconfigured or unapproved external features disabled.

## Acceptance criteria
- Duplicate submission prevented
- ID-only lookup impossible
- token scope and revocation tested
- no internal IDs exposed
- submission is transactional

## Validation
- Intake validation tests
- concurrency/numbering tests
- token authorization tests
- rate-limit tests
- Run every applicable command documented in `AGENTS.md`.
- Record exact results and any environment limitations.

## Completion report
Use the 12-part completion report in `AGENTS.md`.

## Stop point
Stop after guest security and UX review.

End exactly:

`TASK COMPLETE — AWAITING REVIEW`
