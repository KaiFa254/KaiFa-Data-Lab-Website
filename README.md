# KaiFa Data Lab

> **Every Data Problem. One Lab.**
> A data-education, digital-product, project-services and consulting platform —
> and the capstone project of KaiFa's AI-assisted software development course.

---

## What this repository is

This folder holds **everything** that makes up the KaiFa Data Lab website:
the code, the documentation, the tests and the deployment settings.

Right now (Level 0) it contains **documentation and folder structure only**.
Application code is added lesson by lesson, so every file is understood
before it exists. That is deliberate — see `docs/DECISIONS.md`, ADR-000.

## What the finished platform will do

| Area | Visitors can… |
|---|---|
| Learn | Read free SQL, Excel, Power BI, Python, data-science and AI content |
| Store | Buy digital products: cheat sheets, templates, e-books, project packs |
| Services | Submit project work, book consulting, request corporate training |
| Newsletter | Subscribe (with confirmed consent) to tutorials and announcements |
| Account | See orders, download purchases, track projects and proposals |

KaiFa (the admin) can manage products, orders, customers, project requests,
proposals, deliverables, content and subscribers.

## How the repository is organised

```text
kaifa-data-lab/
├── README.md            ← you are here: what this is and how to run it
├── CLAUDE.md            ← instructions Claude Code reads automatically
├── AGENTS.md            ← instructions for ANY coding agent (Codex, Claude…)
├── CHANGELOG.md         ← human-readable history of releases
├── .gitignore           ← files Git must never track (secrets, databases…)
├── .env.example         ← list of settings the app needs, with NO real values
│
├── docs/                ← design documents (read these before coding)
│   ├── ARCHITECTURE.md  ← how the system is built and what talks to what
│   ├── DATABASE.md      ← data model, ERD, migration rules
│   ├── API.md           ← every endpoint: method, path, input, output
│   ├── SECURITY.md      ← security rules and threat checklist
│   ├── DEPLOYMENT.md    ← environments, hosting, release steps
│   ├── INTEGRATIONS.md  ← every outside service and how we connect to it
│   └── DECISIONS.md     ← Architecture Decision Records (why we chose X)
│
├── app/                 ← the application (one FastAPI "modular monolith")
│   ├── core/            ← settings, database connection, shared helpers
│   ├── auth/            ← registration, login, roles
│   ├── products/        ← catalogue: e-books, templates, project packs
│   ├── orders/          ← orders and order items
│   ├── payments/        ← payment attempts, webhooks, refunds
│   ├── downloads/       ← entitlements and secure file links
│   ├── services/        ← project requests, proposals, projects
│   ├── content/         ← articles and tutorials
│   ├── newsletter/      ← subscribers and consent
│   ├── admin/           ← admin-only pages and actions
│   ├── templates/       ← HTML pages
│   └── static/          ← CSS, JavaScript, images
│
├── migrations/          ← step-by-step database changes (Level 8)
├── tests/               ← automated tests (from Level 2 onward)
├── scripts/             ← one-off helper scripts (seed data, backups)
└── data/seed/           ← SAFE sample data for development
```

Each folder contains its own short `README.md` explaining what belongs there.

## How to run it

Filled in at **Level 2**, when the first runnable code exists.

## Current status

See `CHANGELOG.md` and the course progress block in the workbook.
