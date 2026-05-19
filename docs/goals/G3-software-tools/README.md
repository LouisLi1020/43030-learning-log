# G3 — Software development tools (CI/CD)

**Status:** Met (Software Development Tools module + GitHub Actions on SUNishop).

## Evidence in this folder

| File | What it shows |
|------|----------------|
| [ci-and-testing.md](ci-and-testing.md) | Pipeline goals and reviewer evidence |
| [ci-workflow.yml](ci-workflow.yml) | Reference workflow (aligned with app repo `.github/workflows/ci.yml`) |

## What I implemented on SUNishop (May 2026)

See [SUNishop project profile](../../projects/sunishop.md).

| Step | Tooling |
|------|---------|
| Trigger | GitHub Actions on push/PR to `main` |
| Server | `npm ci` → TypeScript check → ESLint → Jest (8 tests) → `npm audit` (report) |
| Client | `npm ci` → Vite production build |
| Outcome | CI fails if validation, sanitisation, or build regresses |

**Why evidence lives here:** Product README stays storefront-focused; this learning log holds professional-development artefacts.

## What I learned

- CI turns “done” into an explicit, repeatable bar (types, lint, tests, client build).
- Tests for security middleware make G2 controls hard to regress accidentally.
