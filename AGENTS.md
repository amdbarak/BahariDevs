# AGENTS.md — BahariDevs Repository Rules

These instructions apply to Codex and any other coding agent working in this repository.

## 1. Authority and reading order

Before work, read:
1. this file;
2. `docs/00_MASTER_PROJECT_SPEC.md`;
3. the remaining numbered `docs/*.md` files;
4. `.agent/PLANS.md`;
5. `tasks/README.md`;
6. the one active task file.

If documents conflict, stop implementation and report the conflict. The owner is the final approver.

## 2. Task isolation

- Implement only one approved task.
- Do not begin future tasks.
- Do not perform unrelated refactors.
- Do not create speculative features.
- Keep commits and changes reviewable.
- Update the active ExecPlan as decisions and progress change.
- End at the task stop point.

## 3. Technical baseline

Subject to successful hosting preflight:
- Laravel `^13.0`
- production PHP 8.4 as the compatibility baseline; PHP 8.5 may be used only after the host and all required extensions are verified
- MariaDB, minimum verified version 10.6; prefer a currently supported host version
- official Laravel Livewire starter architecture
- Blade + Livewire 4 + Alpine.js
- Tailwind CSS 4
- Vite
- Pest 4 or PHPUnit 13-compatible test tooling as selected during repository bootstrap
- database-backed queue and cache defaults unless better infrastructure is verified
- timezone `Africa/Dar_es_Salaam`
- locale `en`; future `sw` localization must remain structurally possible
- currency `TZ`

Never upgrade a major dependency inside an unrelated task.

## 4. Architecture rules

- Use a modular Laravel monolith.
- Organize code by coherent domain boundaries without creating microservices.
- Keep controllers and Livewire actions thin.
- Put business transitions in explicit application/domain services.
- Use Form Requests or equivalent Livewire validation objects.
- Use Policies/Gates for every protected resource.
- Use backed enums for roles, statuses, priority, delivery mode, visibility, and document state.
- Use transactions for multi-record business operations.
- Dispatch notifications/jobs only after successful transaction commit.
- Avoid repositories that merely wrap Eloquent without meaningful abstraction.
- Prevent N+1 queries and unbounded lists.
- Paginate all growing admin and client collections.
- Use database constraints and indexes, not application checks alone.
- Use ULIDs or UUIDs for externally exposed entity references where appropriate.
- Never authorize access using a sequential business number alone.

## 5. Frontend and design rules

- Build original interfaces from the approved BahariDevs design system.
- Do not clone inspiration sites.
- Use semantic HTML and progressive enhancement.
- Target WCAG 2.2 AA.
- Keyboard navigation, focus states, reduced motion, contrast, labels, errors, and screen-reader announcements are required.
- Dark mode is default; light mode is supported.
- Avoid excessive glassmorphism, neon effects, generic stock-tech imagery, autoplay media, cursor hijacking, and motion that obscures content.
- Do not ship unlicensed font files. Use approved self-hosted assets only; otherwise use the documented fallback stack.

## 6. Security rules

Always evaluate:
- authentication and 2FA;
- authorization and IDOR;
- CSRF;
- rate limiting and abuse;
- validation and output escaping;
- mass assignment;
- secure file handling;
- audit logging;
- session and cookie security;
- webhook signature verification;
- secrets and environment separation;
- privacy, retention, deletion, and export.

Never:
- commit secrets or real customer data;
- place private uploads under a public web path;
- trust file extensions;
- log message bodies, tokens, passwords, 2FA secrets, or full attachment contents;
- expose provider credentials to browser code;
- disable TLS verification;
- use `env()` outside configuration files.

## 7. Data and migrations

Before a migration:
- document affected entities;
- define keys, indexes, unique constraints, nullability, and deletion behavior;
- preserve audit/history requirements;
- provide factories and safe seeders;
- test clean migration and rollback where practical.

Use soft deletion only when business and privacy behavior are explicitly defined. Do not use cascading deletion for auditable financial or lifecycle records without an approved policy.

## 8. Testing and quality commands

The exact commands are established in Task 01 and then maintained here. The expected baseline is:

```bash
composer validate --strict
composer install --no-interaction
php artisan test
./vendor/bin/pint --test
./vendor/bin/phpstan analyse
npm ci
npm run build
```

When browser tests exist, run the documented critical-path suite.

For each change:
- test success paths;
- test validation failures;
- test authorization failures;
- test state guards;
- test privacy boundaries;
- test relevant race/idempotency behavior;
- test notifications/webhooks with fakes;
- test file access and retention rules.

Do not delete or weaken a test merely to make the suite pass.

## 9. Dependency policy

- Prefer Laravel and PHP standard capabilities.
- Use maintained packages with compatible licences.
- Record package name, purpose, licence, maintenance signal, and rejected alternatives in the ExecPlan.
- No paid dependency may be assumed.
- No third-party analytics, CAPTCHA, chat, font, or tracking service without explicit approval and privacy documentation.

## 10. Content integrity

- No fabricated testimonials, clients, certifications, guarantees, metrics, project outcomes, staff biographies, or legal claims.
- Placeholder content must be clearly marked and must not appear in production seed data.
- The 24-hour response claim may only be shown if approved operationally; otherwise use non-guaranteed language.
- Draft legal pages are not legal advice and require owner/legal review.

## 11. Completion report

At task completion, report:
1. objective completed;
2. files changed;
3. database changes;
4. architectural decisions;
5. dependencies added;
6. tests added/updated;
7. commands run and results;
8. manual verification steps;
9. security/privacy considerations;
10. accessibility/performance checks;
11. known limitations and open risks;
12. work intentionally deferred.

End exactly:

`TASK COMPLETE — AWAITING REVIEW`
