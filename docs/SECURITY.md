# SECURITY.md

**Why this document exists:** security is a set of rules applied every day,
not a feature added at the end.

## Non-negotiable rules

- [ ] No secrets in Git. Real values only in `.env` / the host's secret settings.
- [ ] Passwords stored only as strong hashes (never plain or reversible).
- [ ] HTTPS everywhere in production.
- [ ] No card data or M-Pesa PINs stored — provider references only.
- [ ] Payments marked paid only after verified webhook / provider API check.
- [ ] Webhooks: signature verified, idempotent, logged.
- [ ] Private files served only through authorised, short-lived signed links.
- [ ] Uploads: size limit, allow-list of types, content sniffing, renamed, private.
- [ ] All SQL parameterised (ORM); no string-built queries.
- [ ] Output escaped in HTML templates (prevents XSS).
- [ ] CSRF protection on forms that change data.
- [ ] Rate limits on login, registration, password reset and forms.
- [ ] Admin actions written to an audit log.
- [ ] Least-privilege database roles; production app is never a superuser.
- [ ] Backups taken **and** a restore tested.

## Threat checklist per feature

For every feature ask: who can call this? what if they lie about who they are?
what if they send huge or malicious input? what if they repeat it 1,000 times?
what is logged?

## Legal and compliance (to confirm with professionals)

Kenya Data Protection Act 2019 obligations, privacy policy, terms, refund policy,
tax on digital sales, receipts/invoices. Not legal advice — to be confirmed.
