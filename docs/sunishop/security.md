# Security notes — SUNishop API

**Application:** [SUNi-Make-Your-Day-Shining](https://github.com/LouisLi1020/SUNi-Make-Your-Day-Shining)

## Scope

Security improvements considered for the Express/MongoDB API: injection risks, authentication, input validation, headers, and abuse limits.

## Threats and mitigations

| Area | Risk | Mitigation |
|------|------|------------|
| Injection | NoSQL operators in JSON (`$gt`, `$where`) | Strip `$` / `.` keys on body, query, params |
| Authentication | Credential stuffing | Rate limits on auth routes; JWT; bcrypt passwords (8+ chars) |
| Input | Bad pagination / email | Validators on register, login, product list queries |
| Misconfiguration | Missing headers, large bodies | Security headers; 1mb JSON cap; disable `x-powered-by` |
| Abuse | API flooding | Per-IP rate limit on `/api` |

## References

- [OWASP Top 10](https://owasp.org/Top10/)
- Secure coding practice from professional cybersecurity study (2026)

## Status

Describes planned and/or applied hardening on the application repo. Verify against latest `main` branch when reviewing code.
