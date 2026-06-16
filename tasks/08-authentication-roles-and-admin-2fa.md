# Task 08 — Authentication, roles, and admin 2FA

## Objective
Implement secure controlled accounts for admin, staff, and technicians.

## Dependencies
- All prior tasks approved, unless an approved task amendment says otherwise.
- Relevant open items in `docs/09_DECISIONS_AND_OPEN_ITEMS.md` resolved or explicitly feature-flagged.

## In scope
- Invite/admin-created users
- login/reset/verification
- roles and policies foundation
- mandatory admin TOTP 2FA
- disable/session revoke
- audit auth events

## Non-goals
- No client accounts
- No social login

## Required implementation behavior
- Inspect the existing repository before changing files.
- Create/update `.agent/active-plan.md`.
- Follow `AGENTS.md` architecture, security, privacy, accessibility, and quality rules.
- Add/update appropriate automated tests.
- Do not weaken earlier acceptance criteria.
- Update affected documentation and ADRs.
- Keep unconfigured or unapproved external features disabled.

## Acceptance criteria
- Public registration unavailable
- Admin cannot access privileged area until 2FA configured
- Disabled user sessions are revoked
- Role boundaries are tested

## Validation
- Authentication and throttling tests
- 2FA gate tests
- role/policy tests
- Run every applicable command documented in `AGENTS.md`.
- Record exact results and any environment limitations.

## Completion report
Use the 12-part completion report in `AGENTS.md`.

## Stop point
Stop after security review.

End exactly:

`TASK COMPLETE — AWAITING REVIEW`
