# G2 — Cybersecurity

**Status:** Met (43030 cybersecurity module + applied secure coding on SUNishop).

## Evidence in this folder

| File | What it shows |
|------|----------------|
| [security-threats-and-mitigations.md](security-threats-and-mitigations.md) | OWASP-aligned threats and mitigations for SUNishop API |
| [cake-rbac-baseline.md](cake-rbac-baseline.md) | Prior JWT + RBAC patterns on CAKE (baseline before SUNishop hardening) |

## What I implemented on SUNishop (May 2026)

Full stack context: [SUNishop project profile](../../projects/sunishop.md).

| Control | Implementation |
|---------|----------------|
| NoSQL injection | Middleware strips `$` / `.` keys from `body`, `query`, `params` |
| Input validation | Auth and product-list validators (email, pagination, password rules) |
| Auth abuse | Rate limits on auth routes; bcrypt (8+ chars); JWT |
| HTTP hardening | Security headers, 1 MB JSON cap, `x-powered-by` disabled |
| Verification | Jest tests for middleware and validation (8 tests on `main`) |

**Application repo:** [SUNi-Make-Your-Day-Shining](https://github.com/LouisLi1020/SUNi-Make-Your-Day-Shining) — evidence in **code**: `server/src/middleware/`, `server/src/__tests__/` (not coursework docs on the product repo).

## What I learned

- JWT + bcrypt alone do not satisfy “secure API”; injection and validation gaps are testable with OWASP framing.
- RBAC on CAKE taught role separation; G2 added **defence in depth** (sanitisation, limits, automated regression tests).
