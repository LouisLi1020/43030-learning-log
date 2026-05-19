# G4 — System design & cloud

**Status:** Met (external courses completed May 2026 + architecture/deployment docs).

## Evidence in this folder

| File | What it shows |
|------|----------------|
| [external-courses.md](external-courses.md) | Completed GCP, Azure, and system design modules (with links) |
| [sunishop-architecture.md](sunishop-architecture.md) | MERN monolith, layers, scale-out trade-offs |
| [sunishop-deployment.md](sunishop-deployment.md) | AWS history, local/docker dev, paused live hosting |
| [rebo-multiplatform-architecture.md](rebo-multiplatform-architecture.md) | Flutter multi-target architecture |

## SUNishop — applied learning (not only courses)

Course study is listed in [external-courses.md](external-courses.md). **Applied** evidence is on the project:

| Topic | Where documented |
|-------|------------------|
| Tech stack & May 2026 engineering | [SUNishop project profile](../../projects/sunishop.md) |
| Monolith vs microservices | [sunishop-architecture.md](sunishop-architecture.md) |
| Cloud deploy paused (credits) | [sunishop-deployment.md](sunishop-deployment.md) |

**Stack (summary):** React 18 + Vite + TypeScript + Tailwind + Zustand · Express + TypeScript · MongoDB/Mongoose · JWT · Stripe · Docker · GitHub Actions.

## What I learned

- GCP/Azure fundamentals complement prior AWS work on SUNishop.
- System design for a solo MERN app: monolith first, document scale path (replicas, CDN, managed DB) without premature microservices.
- Honest deployment narrative when cloud credits end — keep CI and architecture docs active.
