# Version 4: Production Configuration (Current)

**Date**: December 2024
**Status**: Active

## Current Infrastructure

### Hosting
- **VPS**: Hostinger VPS (2GB RAM, 2 vCPU)
- **Management**: Coolify (self-hosted PaaS)
- **Domain**: blkoutuk.cloud (with subdomains)

### Services
| App | URL | Tech Stack |
|-----|-----|------------|
| Events | events.blkoutuk.cloud | React + Vite |
| News | news.blkoutuk.cloud | React + Vite |
| Comms | comms.blkoutuk.cloud | React + Vite |
| Blog | blog.blkoutuk.cloud | React + Vite |
| IVOR | ivor.blkoutuk.cloud | FastAPI + Python |
| Movement | movement.blkoutuk.cloud | React + Vite |

### Database
- Supabase (managed PostgreSQL)
- Used for: events, news, user data

### External APIs
- GROQ (AI inference for IVOR)
- Google Sheets (some data sources)

## Best Practices Established

1. **Dockerfile Pattern**: Multi-stage builds with nginx for SPAs
2. **Environment Variables**: Stored in Coolify, never in code
3. **Deployments**: Git-based auto-deploy on push
4. **Monitoring**: Coolify dashboard + logs
5. **Backups**: Supabase automated backups

## Costs
- Hostinger VPS: ~£10/month
- Supabase: Free tier
- Domain: ~£10/year
- **Total**: ~£130/year for full platform
