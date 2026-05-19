# CI and automated testing

**Application:** [SUNi-Make-Your-Day-Shining](https://github.com/LouisLi1020/SUNi-Make-Your-Day-Shining)

## Pipeline goals

On each push/PR to the application repository:

1. Install server dependencies (`npm ci`)
2. Type-check server TypeScript
3. Lint server code
4. Run Jest tests (security middleware, validation, health routes)
5. Build client (Vite production build)

## Workflow reference

See [ci-workflow.yml](ci-workflow.yml) in this folder for a GitHub Actions template aligned with the MERN layout (`server/`, `client/`).

## Evidence for reviewers

- Screenshot of a green workflow run (attach in portfolio submission)
- Test count and purpose: fail CI when validation or sanitisation regresses

## Why separate from the app repo

Keeps the product repository README focused on the storefront; this log holds professional development artefacts.
