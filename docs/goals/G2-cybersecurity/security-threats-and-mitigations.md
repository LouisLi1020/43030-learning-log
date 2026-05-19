# Security notes — SUNishop API

**Application:** [SUNi-Make-Your-Day-Shining](https://github.com/LouisLi1020/SUNi-Make-Your-Day-Shining)  
**Project profile:** [SUNishop](../../projects/sunishop.md)

## Scope

Security improvements applied to the Express/MongoDB API: injection risks, authentication, input validation, headers, and abuse limits.

## Threats and mitigations

| Area | Risk | Mitigation |
|------|------|------------|
| Injection | NoSQL operators in JSON (`$gt`, `$where`) | Strip `$` / `.` keys on body, query, params |
| Authentication | Credential stuffing | Rate limits on auth routes; JWT; bcrypt passwords (8+ chars) |
| Input | Bad pagination / email | Validators on register, login, product list queries |
| Misconfiguration | Missing headers, large bodies | Security headers; 1mb JSON cap; disable `x-powered-by` |
| Abuse | API flooding | Per-IP rate limit on `/api` |

## Implementation map (code)

| Concern | Typical location in app repo |
|---------|------------------------------|
| Sanitisation middleware | `server/src/middleware/` |
| Auth validation | register/login validators |
| Tests | `server/src/__tests__/` (Jest) |

## References

- [OWASP Top 10](https://owasp.org/Top10/)
- Professional cybersecurity study (2026)

## Status

Applied on SUNishop `main` (May 2026): security middleware, validation, and tests in `server/src/middleware/` and Jest under `server/src/__tests__/`.
