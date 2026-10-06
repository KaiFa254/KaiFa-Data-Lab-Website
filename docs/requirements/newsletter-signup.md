# Requirement: Newsletter signup

**Status:** Draft · **Module:** app/newsletter · **Planned level:** 15

## User story
As a visitor, I want to subscribe to the newsletter
so that I get new tutorials by email.

## Acceptance criteria
1. Valid email → subscriber saved as PENDING; confirmation email sent.
2. Invalid email → clear error message; nothing saved.
3. Confirmation link clicked within 48 hours → status CONFIRMED, timestamp recorded.
4. Expired or tampered link → error page; status unchanged.
5. Same email submitted twice → no duplicate; confirmation re-sent if still PENDING.
6. Every newsletter contains a working one-click unsubscribe link.

## Out of scope (for now)
- Choosing topics or frequency
- Paid newsletters

## Why consent needs confirmation
(Typing an email address does not prove that the person who owns that email actually requested the subscription, so they must confirm through their email.)