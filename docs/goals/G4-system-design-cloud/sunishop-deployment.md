# Deployment notes — SUNishop

**Application:** [SUNi-Make-Your-Day-Shining](https://github.com/LouisLi1020/SUNi-Make-Your-Day-Shining)  
**Project profile:** [SUNishop](../../projects/sunishop.md)

## AWS (historical)

Designed for MERN on AWS (app server + MongoDB). Cloud credits are exhausted; **no live instance** is running now.

Conceptual layout:

- Client: Vite build → S3 + CloudFront
- API: Node on EC2 or container
- Data: MongoDB Atlas or self-hosted

## Local development

```bash
docker-compose up -d   # if using project compose file

cd server && cp env.example .env && npm install && npm run dev
cd client && npm install && npm run dev
```

## CI without production deploy

GitHub Actions can run tests and client build without AWS secrets — see [G3 — CI & testing](../G3-software-tools/ci-and-testing.md).

## Resuming cloud hosting

1. MongoDB Atlas + `MONGODB_URI`
2. Secrets via environment only (`JWT_SECRET`, Stripe keys)
3. Deploy API; set `CLIENT_URL` to frontend origin
