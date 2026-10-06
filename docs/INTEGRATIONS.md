# INTEGRATIONS.md

**Why this document exists:** every outside service is a dependency that can
cost money, leak data or go down. Each one must be understood before it's added.

## Template — answer all ten for every integration

1. What it does
2. Why we need it (do we need it *now*?)
3. What data moves through it
4. How it connects (API, webhook, SDK, DNS)
5. Authentication method
6. Cost (free tier, learning cost, production cost)
7. Security implications
8. Failure modes
9. Alternative providers
10. What happens if the provider goes down

## Integration map

| Integration | Needed from | Status |
|---|---|---|
| GitHub | Level 3 | Chosen |
| Claude Code | Level 5 | Chosen (Claude Pro) |
| Codex | Level 6 | Chosen (ChatGPT Free) |
| GitHub MCP | Level 7 | TO VERIFY |
| Database (SQLite → PostgreSQL) | Level 8 | PostgreSQL availability on Truehost TO VERIFY |
| Hosting + domain + DNS + HTTPS | Level 10 | Truehost cPanel — TO VERIFY Python app support |
| Payment provider | Level 12 | Candidates TO VERIFY: Kenyan M-Pesa + card gateways |
| Object storage | Level 13 | TO VERIFY: free-tier S3-compatible storage |
| Email provider | Level 15 | TO VERIFY: free-tier transactional + newsletter |
| Scheduling tool | Level 15 | TO VERIFY: external booking tool vs build |
| Error tracking + uptime | Level 20 | TO VERIFY: free tiers |
| LLM provider | Level 22 | Free tier TO VERIFY |

Each row gets its own section, using the template, when it is added.
