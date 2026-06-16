# Task Backlog

Run tasks in order unless the owner approves a documented dependency-safe change.

| # | Task | File |
|---:|---|---|
| 00 | Hosting and repository preflight | `00-hosting-and-repository-preflight.md` |
| 01 | Repository foundation and quality gates | `01-repository-foundation.md` |
| 02 | Domain model and ERD | `02-domain-model-and-erd.md` |
| 03 | Design system and application shell | `03-design-system-and-application-shell.md` |
| 04 | Public home page | `04-public-home-page.md` |
| 05 | Company, services, solutions, and industries pages | `05-public-company-services-solutions.md` |
| 06 | Portfolio, blog, contact, and legal surfaces | `06-portfolio-blog-contact-and-legal.md` |
| 07 | Public SEO, accessibility, and performance release gate | `07-public-seo-accessibility-performance.md` |
| 08 | Authentication, roles, and admin 2FA | `08-authentication-roles-and-admin-2fa.md` |
| 09 | Guest request intake and secure tracking | `09-guest-request-intake-and-tracking.md` |
| 10 | Private file management | `10-private-file-management.md` |
| 11 | Service-item workflow engine | `11-item-workflow-engine.md` |
| 12 | Technician specialties and assignments | `12-technician-specialties-and-assignment.md` |
| 13 | Scheduling, service zones, travel fees, and conflicts | `13-scheduling-zones-and-conflicts.md` |
| 14 | Request communication threads | `14-request-communications.md` |
| 15 | Email and WhatsApp notification adapters | `15-email-whatsapp-notifications.md` |
| 16 | Quotations and acceptance | `16-quotations.md` |
| 17 | Invoices, external payment records, and receipts | `17-invoices-external-payments-and-receipts.md` |
| 18 | Admin request operations | `18-admin-request-operations.md` |
| 19 | CMS and user management | `19-cms-and-user-management.md` |
| 20 | Analytics, audit viewer, and settings | `20-analytics-audit-and-settings.md` |
| 21 | Privacy, retention, and data rights | `21-privacy-retention-and-data-rights.md` |
| 22 | Security hardening | `22-security-hardening.md` |
| 23 | Deployment, backup, monitoring, and recovery | `23-deployment-backup-monitoring.md` |
| 24 | Final acceptance and launch | `24-final-acceptance-and-launch.md` |

## Per-task workflow
1. Owner approves one task.
2. Codex reads all authority documents and the task.
3. Codex creates/updates `.agent/active-plan.md`.
4. Codex implements only that task.
5. Codex runs required checks.
6. Codex gives the completion report.
7. Codex ends with `TASK COMPLETE — AWAITING REVIEW`.
8. Owner reviews before the next task.

## Marketing release
Tasks 00–07 are the public-site path. A limited secure lead/request form may pull selected Task 09 requirements forward only through an approved task amendment.
