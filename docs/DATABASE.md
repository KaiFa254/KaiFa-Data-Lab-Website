# DATABASE.md

**Why this document exists:** the database outlives the code. Its design
decisions must be written down and reviewed.

## Principles

1. Design the data model (ERD) **before** writing tables.
2. Only build the tables version 1 actually needs.
3. Separate concepts get separate tables (order ≠ payment ≠ entitlement).
4. Money is stored as an integer in the smallest unit with a currency code
   (e.g. `amount_minor = 250000`, `currency = 'KES'` means KES 2,500.00).
5. Large files live in object storage; the database stores only their metadata.
6. Every schema change is a reviewed migration file.
7. The application uses a least-privilege database role, never a superuser.

## Environments

| Database | Purpose | Data |
|---|---|---|
| Development | Your laptop | Synthetic seed data |
| Test | Automated tests; rebuilt every run | Test fixtures |
| Production | Real customers | Real data — backed up, restore-tested |

## ERD

Created at Level 8.

## Entity list

Candidate v1 entities are chosen at Level 8, from the full list in the workbook.
