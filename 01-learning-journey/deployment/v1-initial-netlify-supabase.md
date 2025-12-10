# Version 1: Initial Netlify + Supabase Deployment

**Date**: Early 2024
**Status**: Superseded
**Apps**: Events Calendar, Comms

## Architecture
- Frontend: Netlify (static hosting)
- Backend: Supabase (database + edge functions)
- Build: Vite

## Key Learnings
1. Netlify free tier limitations for build minutes
2. Supabase edge functions cold start issues
3. CORS configuration challenges

## Configuration
```toml
# netlify.toml
[build]
  command = "npm run build"
  publish = "dist"
```

## Environment Variables
- VITE_SUPABASE_URL
- VITE_SUPABASE_ANON_KEY
