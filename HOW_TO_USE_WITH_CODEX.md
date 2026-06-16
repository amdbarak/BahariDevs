# How to Use This Package with Codex

## 1. Create a private repository

Create a private Git repository for the BahariDevs project. Add this specification package at the repository root before implementation.

Expected root files include:
- `AGENTS.md`
- `CODEX_START_PROMPT.md`
- `docs/`
- `tasks/`
- `.agent/PLANS.md`

Do not add production credentials.

## 2. Add approved brand assets

Place owner-supplied assets in a clearly named source directory such as:
```text
project-inputs/brand/
```

Include licence/provenance notes. Do not place unlicensed Satoshi font files in the repository.

## 3. Start only Task 00

Open Codex against the repository and paste `CODEX_START_PROMPT.md`.

Do not ask Codex to “build everything.” The first job is environment and repository preflight.

## 4. Review the completion report

For every task:
- inspect the diff;
- read the ExecPlan;
- confirm tests actually ran;
- verify screenshots/manually test when UI changes;
- review limitations and blockers;
- reject fabricated content or assumptions;
- approve the next task explicitly.

## 5. Approve the next task

Use `templates/NEXT_TASK_PROMPT.md`, replacing the task filename.

## 6. Keep secrets outside prompts and commits

Provide credentials through approved Codex/environment secret mechanisms or configure them manually in staging/production. Never paste real provider keys into documentation.

## 7. Treat provider work as gated

Mailgun, Meta WhatsApp, DNS, hosting, monitoring, and legal/tax behavior need real external setup. Code can be implemented behind feature flags before credentials are ready, but must not be called production-ready.

## 8. Use staging

Do not deploy the first working version directly to production. Validate migrations, queues, cron, storage, webhooks, private downloads, emails, backups, and rollback in staging.

## 9. Marketing launch

For 20 June 2026, prioritize Tasks 00–07. Pull a limited request/lead intake forward only through a written task amendment that preserves Task 09 security controls.

## 10. Full platform

Continue Tasks 08–24 after the public release. Do not skip workflow, privacy, security, backup, or acceptance tasks.
