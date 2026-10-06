# API.md

**Why this document exists:** the API is the contract between the browser
and the backend. Writing it down prevents guessing.

## Conventions (explained at Level 9)

- JSON in, JSON out for `/api/...` routes; HTML pages for browser routes.
- Nouns in paths, HTTP methods as verbs: `GET /api/products`, `POST /api/orders`.
- Standard status codes: 200 OK, 201 Created, 400 bad input, 401 not logged in,
  403 not allowed, 404 not found, 409 conflict, 422 validation error, 500 server error.
- FastAPI generates interactive documentation at `/docs` automatically.

## Planned endpoints (v1)

| Method | Path | Purpose | Auth |
|---|---|---|---|
| GET | /health | Is the app alive? | Public |
| GET | /api/products | List products | Public |
| GET | /api/products/{slug} | One product | Public |
| POST | /api/newsletter/subscribe | Start double opt-in | Public |
| POST | /api/orders | Create an order | Customer |
| POST | /api/payments/webhook/{provider} | Provider confirms payment | Provider signature |
| GET | /api/downloads/{entitlement_id} | Get a signed download link | Owner only |
| POST | /api/project-requests | Submit a project | Customer |
| GET | /api/projects/{id} | Project status | Owner or admin |

Details added as each endpoint is built.
