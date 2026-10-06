# DECISIONS.md — Architecture Decision Records (ADRs)

**Why this document exists:** months from now, "why did we do it this way?"
must have a written answer. Each important decision gets a short record.
Records are never deleted; a later ADR can supersede an earlier one.

## Template

```text
ADR-NNN: Title
Status: Proposed | Accepted | Superseded by ADR-XXX
Date:
Context:   what problem or constraint forced a decision
Options:   what we considered
Decision:  what we chose
Consequences: what gets easier, what gets harder
```

---

### ADR-000: Build lesson by lesson, not all at once
Status: Accepted · Date: 2026-09-29
Context: The owner is learning; generated code nobody understands is a liability.
Decision: Code is added only in the lesson that teaches it, with full comments.
Consequences: Slower start; every file is understood and reviewable.

### ADR-001: Modular monolith
Status: Accepted · Date: 2026-09-29
Context: Solo developer, early business, limited hosting.
Options: Microservices; single unstructured app; modular monolith.
Decision: One FastAPI app with clear internal modules.
Consequences: Simple deploys and debugging; modules can be extracted later if needed.

### ADR-002: FastAPI with server-rendered HTML first
Status: Accepted · Date: 2026-09-29
Context: The owner should learn the browser, forms and HTTP before any framework.
Decision: FastAPI serves HTML templates plus small vanilla JavaScript.
Consequences: Less tooling; a frontend framework is evaluated later only if needed.

### ADR-003: SQLite for development, PostgreSQL for production
Status: Proposed · Date: 2026-09-29
Context: Zero-setup start; production needs concurrency and real roles.
Decision pending: PostgreSQL availability on hosting (Level 8).

### ADR-004: Hosting on Truehost cPanel first
Status: Proposed · Date: 2026-09-29
Context: Owner already pays for Truehost; cost matters.
Decision pending: verify Python app support and resource limits (Level 10).

### ADR-005: Payment provider
Status: Open
Decision made at Level 12 after checking current Kenya support, fees,
currencies (KES/USD), M-Pesa, cards, webhooks and documentation.

### ADR-006: Launch on a subdomain
Status: Accepted · Date: 2026-09-29
Context: Need a live address now at no cost; Data Lab is a separate brand from Erakan.
Decision: Launch on kaifadatalab.erakansystems.co.ke. A dedicated KaiFa Data Lab
domain can be added later without code changes (the site address lives in APP_BASE_URL).
Consequences: Free and immediate, with HTTPS via AutoSSL. The URL is long and carries
Erakan's name, so a dedicated domain is likely before a public marketing push.

### ADR-007: Python 3.12
Status: Accepted · Date: 2026-09-29
Context: Truehost offers Python up to 3.12.14; the laptop has 3.13 via Anaconda.
Decision: The project uses Python 3.12 both locally (installed by uv at Level 2)
and on the server.
Consequences: Same behaviour in development and production. Anaconda stays
separate for other data-science work.