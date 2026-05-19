# RBAC and security — CAKE

**Application:** [CAKE-Making-Every-Task-a-Piece-of-Cake.](https://github.com/LouisLi1020/CAKE-Making-Every-Task-a-Piece-of-Cake.)  
**Project profile:** [CAKE](../../projects/cake.md)

## Context

CAKE is a full-stack task and lightweight CRM system. It established my baseline in **role-based access control** before applying newer secure-SDLC practice on SUNishop.

## Authentication

- JWT-based sessions
- bcrypt password hashing
- API documented via Swagger (`/api-docs`)

## Roles

| Role | Typical permissions |
|------|-------------------|
| **Manager** | Full system access, user management |
| **Leader** | Task assignment, client management |
| **Member** | Task execution, status updates |

## Security-relevant features

- Role checks on protected routes
- Dockerised dev/prod parity (`docker-compose.yml`)
- Environment-based secrets (`server/.env`, not committed)

## Relation to later work

Patterns from CAKE (auth + RBAC) informed what I improved on SUNishop: stricter input validation, injection-aware middleware, and automated tests — documented in [G2 — SUNishop security](security-threats-and-mitigations.md).

## Verification

See the application repo README and `docs/` for current implementation status (M5.5).
