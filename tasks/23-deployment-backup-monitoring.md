# Task 23 — Deployment, backup, monitoring, and recovery

## Objective
Create and verify a repeatable cPanel-compatible release and recovery process.

## Dependencies
- All prior tasks approved, unless an approved task amendment says otherwise.
- Relevant open items in `docs/09_DECISIONS_AND_OPEN_ITEMS.md` resolved or explicitly feature-flagged.

## In scope
- Staging
- deployment/rollback
- cron/queue
- backups/restore
- health/heartbeat
- alerts
- provider DNS
- runbooks

## Non-goals
- No first-time testing directly in production

## Required implementation behavior
- Inspect the existing repository before changing files.
- Create/update `.agent/active-plan.md`.
- Follow `AGENTS.md` architecture, security, privacy, accessibility, and quality rules.
- Add/update appropriate automated tests.
- Do not weaken earlier acceptance criteria.
- Update affected documentation and ADRs.
- Keep unconfigured or unapproved external features disabled.

## Acceptance criteria
- Staging release succeeds
- restore test evidence exists
- scheduler/queue heartbeat monitored
- rollback works
- web root/private storage safe

## Validation
- Deployment smoke tests
- restore drill
- queue/scheduler checks
- Run every applicable command documented in `AGENTS.md`.
- Record exact results and any environment limitations.

## Completion report
Use the 12-part completion report in `AGENTS.md`.

## Stop point
Stop after operational readiness review.

End exactly:

`TASK COMPLETE — AWAITING REVIEW`
