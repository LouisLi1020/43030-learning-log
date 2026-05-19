# CAKE — project profile (learning evidence)

**Application repo:** [CAKE-Making-Every-Task-a-Piece-of-Cake.](https://github.com/LouisLi1020/CAKE-Making-Every-Task-a-Piece-of-Cake.)  
**Type:** Full-stack task / lightweight CRM  
**Primary goal:** G2 baseline (RBAC before SUNishop hardening)

## Tech stack

| Layer | Technologies |
|-------|----------------|
| Frontend | React |
| Backend | Node.js, Express |
| Database | MongoDB |
| Auth | JWT, bcrypt, role-based routes |
| Ops | Docker Compose, Swagger (`/api-docs`) |

## Roles (RBAC)

| Role | Typical permissions |
|------|---------------------|
| Manager | Full access, user management |
| Leader | Task assignment, clients |
| Member | Execute tasks, update status |

## G2 evidence

- [CAKE RBAC baseline](../goals/G2-cybersecurity/cake-rbac-baseline.md)

## Relation to SUNishop

CAKE established JWT + RBAC patterns; SUNishop (May 2026) added injection-aware middleware, validators, rate limits, and CI-tested security controls — see [SUNishop profile](sunishop.md).
