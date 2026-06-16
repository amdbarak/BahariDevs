# Task 15 — Email and WhatsApp notification adapters

## Objective
Implement reliable provider-neutral outbound notifications and controlled inbound reply processing.

## Dependencies
- All prior tasks approved, unless an approved task amendment says otherwise.
- Relevant open items in `docs/09_DECISIONS_AND_OPEN_ITEMS.md` resolved or explicitly feature-flagged.

## In scope
- Notification matrix/preferences
- Mailgun adapter and SMTP fallback
- Meta Cloud API adapter
- queues/retries
- delivery logs
- webhook verification/idempotency
- inbound normalization/quarantine

## Non-goals
- No credentials committed
- No unapproved template claims
- No WhatsApp upload-only alert

## Required implementation behavior
- Inspect the existing repository before changing files.
- Create/update `.agent/active-plan.md`.
- Follow `AGENTS.md` architecture, security, privacy, accessibility, and quality rules.
- Add/update appropriate automated tests.
- Do not weaken earlier acceptance criteria.
- Update affected documentation and ADRs.
- Keep unconfigured or unapproved external features disabled.

## Acceptance criteria
- Business transaction survives provider failure
- webhook replay rejected
- unknown inbound quarantined
- internal content excluded
- feature flags disable unconfigured channels

## Validation
- Adapter contract tests
- notification matrix tests
- webhook signature/replay tests
- retry tests
- Run every applicable command documented in `AGENTS.md`.
- Record exact results and any environment limitations.

## Completion report
Use the 12-part completion report in `AGENTS.md`.

## Stop point
Stop after sandbox/provider-readiness review.

End exactly:

`TASK COMPLETE — AWAITING REVIEW`
