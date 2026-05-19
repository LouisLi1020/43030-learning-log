# SUNishop — project profile (learning evidence)

**Application repo:** [SUNi-Make-Your-Day-Shining](https://github.com/LouisLi1020/SUNi-Make-Your-Day-Shining)  
**Type:** Full-stack lifestyle e-commerce (side project)  
**Evidence period:** Autumn 2026 (engineering updates on `main`, May 2026)

This document summarises **what the project is**, **what was implemented for professional learning**, and **how it maps to goals G2–G4**. Goal-specific write-ups live under [`docs/goals/`](../goals/README.md).

---

## Tech stack

| Layer | Technologies | Notes |
|-------|----------------|-------|
| **Frontend** | React 18, TypeScript, Vite, Tailwind CSS, Zustand | Figma-based storefront UI; some flows still UI-first |
| **Backend** | Node.js, Express, TypeScript | REST API: auth, products, cart, checkout |
| **Database** | MongoDB, Mongoose | Users, products, orders |
| **Auth** | JWT, bcrypt | Role-aware routes (guest / member / admin concepts) |
| **Payments** | Stripe (env-configured) | Integrated where API complete |
| **DevOps** | Docker Compose (local), GitHub Actions (CI) | AWS deploy **paused** (credits ended) |
| **Prior cloud** | AWS (S3/CloudFront, EC2-style layout documented) | Design retained; live hosting not running |

---

## What the product does (scope)

- Product catalogue, search/filter, cart, checkout flows  
- User registration/login, profiles, order history (API + UI at varying maturity)  
- Admin-oriented pages for catalogue and orders (in progress on UI integration)

README on the app repo distinguishes **“UI ready”** vs **“API integrated”** — honest scope for collaborators and markers.

---

## What I implemented (May 2026 — professional learning)

Engineering work on `main` supports **G2 (security)** and **G3 (tools)**; architecture/deployment notes support **G4**.

### Security (G2)

| Item | Implementation |
|------|----------------|
| NoSQL injection hardening | Middleware strips `$` / `.` keys from `body`, `query`, `params` |
| Input validation | `validateAuth` (register/login), `validateProductQuery` (pagination) |
| Auth abuse | Rate limiting on auth routes; bcrypt passwords (minimum length) |
| HTTP hardening | Security headers, JSON body size cap, `x-powered-by` disabled |
| Tests | Jest suites for middleware and validation (8 tests on server) |

Details: [G2 — security](../goals/G2-cybersecurity/security-threats-and-mitigations.md) · app repo `server/src/middleware/` and `server/src/__tests__/`

### CI/CD & testing (G3)

| Item | Implementation |
|------|----------------|
| GitHub Actions | `.github/workflows/ci.yml` on push/PR to `main` |
| Server job | `npm ci` → type-check → lint → Jest → audit (report) |
| Client job | `npm ci` → Vite production build |
| Definition of done | CI fails if validation/sanitisation regresses |

Details: [G3 — CI](../goals/G3-software-tools/ci-and-testing.md)

### Architecture & deployment (G4)

| Item | Documentation / learning |
|------|---------------------------|
| System design | Monolithic Express API; when to scale (replicas, CDN, managed DB) |
| Deployment | AWS history, local/docker dev, why live deploy paused |
| Cloud study | GCP/Azure modules **plus** applying concepts to this MERN layout |

Details: [G4 — architecture](../goals/G4-system-design-cloud/sunishop-architecture.md) · [deployment](../goals/G4-system-design-cloud/sunishop-deployment.md)

---

## What I learned (reflection)

1. **Security is more than login** — JWT + bcrypt did not cover injection, validation, or rate limits; OWASP framing made gaps testable.  
2. **CI encodes discipline** — pipeline forced explicit “done” (types, lint, tests, client build).  
3. **Honest documentation** — separating learning log from product README kept recruiter-facing repos clean while still showing assessable evidence.  
4. **Reliability vs cost** — when AWS credits ended, I kept architecture and CI green locally instead of overstating production readiness.  
5. **Monolith first** — appropriate for solo scope; documented scale-out path without premature microservices.

---

## Links by goal

| Goal | Evidence in this repo |
|------|------------------------|
| G2 | [G2-cybersecurity/](../goals/G2-cybersecurity/) |
| G3 | [G3-software-tools/](../goals/G3-software-tools/) |
| G4 | [G4-system-design-cloud/](../goals/G4-system-design-cloud/) |
