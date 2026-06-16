# 08 — Deployment and Operations

## 1. Environments

- local development;
- automated test;
- staging on hosting-equivalent infrastructure;
- production.

Never use production as the first environment to test migrations, webhooks, queues, storage permissions, or document generation.

## 2. Hosting preflight

Verify in Task 00:
- exact PHP versions and extensions;
- MariaDB version and SQL mode;
- Composer availability/version;
- Node/npm availability and whether builds occur locally or server-side;
- SSH restrictions;
- cron frequency;
- persistent process support;
- symlink support;
- document-root control;
- outbound SMTP/API connectivity;
- inbound webhook reachability;
- TLS;
- file upload/post limits;
- execution time/memory;
- backup facilities;
- staging/subdomain;
- Redis availability;
- malware scanning;
- cPanel Git/deployment support.

Do not assume a feature because cPanel usually provides it.

## 3. Shared-hosting deployment model

Preferred repository layout:
```text
/home/account/apps/baharidevs/current/   # application
/home/account/public_html/               # public assets or controlled public symlink/copy
/home/account/shared/.env
/home/account/shared/storage/
```

Exact structure depends on host capabilities. The Laravel `public` directory must be the web root. Never expose repository root, `.env`, vendor metadata, storage, or source documents.

## 4. Build and deploy

A repeatable deployment script/checklist should:
1. enable maintenance mode where necessary;
2. fetch/upload verified release;
3. install Composer dependencies with production flags;
4. build assets in CI/local or verified server Node environment;
5. run migrations with appropriate force/backup;
6. link shared storage;
7. cache config/routes/views/events where compatible;
8. restart/reload queue process or bounded worker;
9. disable maintenance mode;
10. run health and smoke checks;
11. support rollback to prior release.

Do not run destructive migrations without backup and rollback planning.

## 5. Scheduler and queue

Required cron:
```text
* * * * * cd /path/to/app && php artisan schedule:run >> /dev/null 2>&1
```

If no persistent worker:
- schedule a bounded `queue:work --stop-when-empty` command with overlap protection;
- monitor lag and failed jobs;
- document that near-real-time delivery depends on cron frequency.

Verify actual PHP CLI path in cPanel.

## 6. Backups

Back up:
- MariaDB;
- private storage;
- public CMS media;
- configuration/secrets through a secure separate process;
- release metadata.

Requirements:
- encrypted where feasible;
- off-account/off-server copy;
- daily database backup;
- daily or risk-based file backup;
- retention schedule;
- restore test before launch and periodically;
- backups honor eventual privacy deletion strategy, with documented expiry rather than unsafe surgical editing.

## 7. Monitoring

At minimum:
- uptime and TLS expiry;
- Laravel error rate;
- queue lag and failed jobs;
- scheduler heartbeat;
- notification/provider failures;
- webhook failures;
- storage usage;
- database availability;
- backup success;
- security events;
- health endpoint.

Alerts must reach a monitored owner channel.

## 8. Email and WhatsApp

Email:
- configure SPF, DKIM, and DMARC;
- validate sending domain;
- use transactional provider credentials;
- process bounces/complaints where provider supports it.

WhatsApp:
- Meta Cloud API preferred;
- approved templates required for business-initiated messages outside allowed windows;
- webhook verification and app secret controls;
- phone-number/business verification is an external launch dependency.

Implement adapters and sandbox tests before real credentials.

## 9. Recovery

Document:
- deployment rollback;
- database restore;
- private-file restore;
- lost `.env`/key response;
- compromised admin response;
- provider credential rotation;
- webhook outage;
- queue backlog;
- accidental purge.

Define RPO/RTO with the owner after hosting capabilities are known.

## 10. Launch checklist

- approved content and assets;
- correct company details;
- domain/TLS;
- production secrets;
- admin 2FA;
- provider verification;
- legal/privacy review;
- backups and tested restore;
- monitoring;
- scheduled jobs;
- queue;
- database indexes;
- security headers;
- error pages;
- sitemap/robots;
- no test accounts/data;
- no placeholder testimonials/projects;
- smoke test on real devices;
- rollback release available.
