# DEPLOYMENT.md

**Why this document exists:** deployments must be repeatable and reversible,
not remembered.

## Environments

| Name | Where | URL |
|---|---|---|
| Development | Your laptop | http://127.0.0.1:8000 |
| Production | Truehost cPanel (first), container host later if needed | https://kaifadatalab.erakansystems.co.ke |

## Hosting plan

### Verified 2026-09-29 (cPanel, Jupiter theme)
- Setup Python App: available
- PostgreSQL Databases: available (0 used)
- SSH Access: available
- Limits: 4 GB RAM, 1 CPU core, 20 entry processes, 50 processes, 29.3 GB disk
- Python versions offered: 3.6–3.12 (newest: 3.12.14) → project uses Python 3.12
- Subdomain: kaifadatalab.erakansystems.co.ke (own document root, separate from public_html)
- SSL: AutoSSL active on the subdomain and www (expires 2026-12-28, auto-renews)
- Force HTTPS: on for the subdomain only

### Still to verify (Level 10)
- FastAPI is ASGI; cPanel's Python app runner (Passenger) expects WSGI.
  Confirm the adapter approach with a small test app.
- Where application logs appear, and how to restart the app.

### Rules
- The Erakan website (public_html) is never touched by this project.
  Separate subdomain, folder, Python app and database.
- Take a full cPanel backup before the first deployment.
- Never commit the cPanel username, passwords, or server IP to Git.
- Docker (Level 18) cannot run on shared cPanel. Docker Desktop is used
  locally; production container hosting is decided at that level.

## Release checklist

Filled in at Level 17.

## Rollback

Filled in at Level 17.