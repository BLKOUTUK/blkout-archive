# Version 3: Coolify Self-Hosted Migration

**Date**: Late 2024
**Status**: Current Production
**Apps**: All platform apps

## Why We Migrated
- Cost control (single VPS vs per-app billing)
- More control over infrastructure
- Better for cooperative ownership model
- No vendor lock-in

## Architecture
- Hosting: Hostinger VPS + Coolify
- Container: Docker (multi-stage builds)
- SSL: Let's Encrypt via Coolify
- Domains: *.blkoutuk.cloud subdomains

## Deployment URLs
- events.blkoutuk.cloud - Events Calendar
- news.blkoutuk.cloud - News Aggregator
- comms.blkoutuk.cloud - SocialSync
- blog.blkoutuk.cloud - Voices Blog
- ivor.blkoutuk.cloud - IVOR AI
- movement.blkoutuk.cloud - Scrollytelling

## Key Learnings
1. Dockerfile configuration critical (base_directory, build_pack)
2. Multi-stage builds reduce image size significantly
3. nginx config needed for SPA routing
4. Coolify API useful for automation

## Configuration
```dockerfile
# Multi-stage Dockerfile pattern
FROM node:20-alpine AS builder
WORKDIR /app
COPY package*.json ./
RUN npm ci
COPY . .
RUN npm run build

FROM nginx:alpine
COPY --from=builder /app/dist /usr/share/nginx/html
```

## Coolify API
- Base URL: https://infra.blkoutuk.cloud
- Used for: deployments, environment variables, logs
