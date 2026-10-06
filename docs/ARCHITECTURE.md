# ARCHITECTURE.md

**Why this document exists:** anyone (human or AI agent) should be able to
understand how the system fits together *before* reading code.

## 1. Big picture

```text
VISITOR'S BROWSER (phone / laptop)
        │  HTTPS
        ▼
DOMAIN + DNS  ──►  HOSTING SERVER (Truehost cPanel first)
                        │
                        ▼
              FASTAPI APPLICATION (one modular monolith)
              ├── auth        ├── payments   ├── content
              ├── products    ├── downloads  ├── newsletter
              ├── orders      ├── services   └── admin
                        │
                        ├──► DATABASE (SQLite → PostgreSQL)
                        ├──► PAYMENT PROVIDER  (M-Pesa, cards)
                        ├──► EMAIL PROVIDER    (receipts, newsletter)
                        ├──► OBJECT STORAGE    (private product files)
                        ├──► SCHEDULING TOOL   (consultations)
                        └──► LLM PROVIDER      (AI features, later)
```

## 2. Why a modular monolith

One deployable application, internally split into modules with clear
boundaries. It is simpler to build, test, deploy and debug than many
microservices, and a solo developer can hold it in their head. If one
module ever needs to scale separately, its clean boundary lets it be
extracted later. See ADR-001.

## 3. Designed to grow without over-engineering

Version 1 has one service provider: KaiFa Data Lab. It is **not** a marketplace.

To allow staff or freelancers later, without building a marketplace now:
- Users have a **role** (visitor, customer, admin; later staff).
- Projects carry an optional `assigned_to` user. In v1 it is always KaiFa.
- There are no bids, provider profiles, escrow or commission tables.
  Those are added only if the business model changes.

## 4. Module responsibilities

Filled in as each module is built (Levels 9–15).

## 5. Request journeys

See the workbook for traced journeys (purchase, project service).
Each module's journey is documented here as it is implemented.
