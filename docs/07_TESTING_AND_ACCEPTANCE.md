# 07 — Testing and Acceptance

## 1. Quality gates

A task is complete only when applicable:
- migrations succeed from an empty database;
- rollback is tested where practical;
- format/lint/static analysis pass;
- unit and feature tests pass;
- production assets build;
- authorization tests pass;
- accessibility/manual keyboard checks pass;
- security/privacy cases pass;
- task documentation and ExecPlan are updated;
- no debug code, secrets, fabricated production content, or skipped failing tests remain.

## 2. Test layers

- unit tests for pure rules, status calculations, money, numbering, adapters;
- feature tests for HTTP/Livewire behavior, validation, policies, persistence;
- integration tests for provider adapters using fakes/recorded safe fixtures;
- browser tests for critical public/admin/technician journeys;
- deployment smoke tests on staging;
- manual exploratory testing for responsive design and assistive behavior.

## 3. Mandatory critical scenarios

1. Guest can submit a valid multi-service request once.
2. Duplicate submit with same idempotency key does not duplicate data.
3. Invalid, oversized, mismatched, or executable files are rejected/quarantined.
4. Sequential request number alone grants no access.
5. Tracking token for one request cannot access another.
6. Revoked/expired token is denied.
7. Staff cannot perform admin-only transition.
8. Technician cannot see unassigned item.
9. Technician cannot start or approve completion.
10. Admin cannot skip workflow state.
11. Required reason/evidence is enforced.
12. Completion submission and approval are auditable.
13. Internal note never appears in guest response, email, or WhatsApp.
14. Download of private attachment is denied without authorization.
15. Reassignment preserves history.
16. Conflicting appointment is blocked under concurrent attempts.
17. On-hold resume restores the correct prior state.
18. Reopening routes to approved destination and records reason.
19. Provider webhook replay is ignored safely.
20. Notification failure does not roll back/corrupt the business transaction.
21. Quote versions and issued invoice snapshots remain consistent.
22. Duplicate document issuance is prevented.
23. Disabled user cannot log in and active sessions are revoked.
24. Admin privileged access requires 2FA.
25. Privacy export excludes other customers.
26. Retention purge respects legal hold and deletes eligible files.
27. CMS rich content cannot store executable script.
28. Draft/scheduled content is not publicly indexable.
29. Theme selection does not flash or break without JavaScript.
30. Public navigation and forms work with keyboard and reduced motion.

## 4. Browser matrix

Minimum current versions at release:
- Chrome/Edge;
- Firefox;
- Safari;
- mobile Safari;
- Android Chrome.

Tailwind 4 requires modern browsers; support targets must not claim older incompatible versions.

## 5. Performance acceptance

Public templates:
- responsive images and dimensions;
- no unbounded third-party scripts;
- no preventable N+1;
- pagination;
- cache strategy;
- production build;
- Lighthouse/real-device review on representative pages.

Initial budgets to validate and adjust:
- LCP target ≤ 2.5s at 75th percentile where measurable;
- CLS ≤ 0.1;
- INP ≤ 200ms;
- initial page JavaScript minimized; public content should not require large SPA bundles;
- hero media generally ≤ 300 KB where quality permits;
- no single nonessential public asset > 500 KB without approval.

These are engineering targets, not guaranteed outcomes on all networks/devices.

## 6. Accessibility acceptance

- automated checks have no known serious/critical errors;
- keyboard walkthrough completed;
- focus order and visibility;
- screen-reader spot checks on navigation, request form, tracking, tables/timelines, dialogs;
- zoom/reflow at 200%/400% where applicable;
- contrast;
- reduced motion;
- error identification and instructions;
- no inaccessible CAPTCHA.

## 7. Test data

- factories for every domain;
- deterministic dates/timezone;
- no real personal data;
- representative Tanzanian and international phone/address cases;
- safe fake provider payloads;
- test file fixtures only;
- seeders separated into development demo vs production essentials.

## 8. Completion evidence

Every task report includes exact commands and pass/fail results. “Looks correct” is not acceptance.
