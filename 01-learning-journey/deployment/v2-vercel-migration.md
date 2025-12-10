# Version 2: Vercel Migration

**Date**: Mid 2024
**Status**: Superseded
**Apps**: Comms, News, Blog

## Why We Migrated
- Better Next.js/React support
- Faster builds
- Edge functions with better performance
- Free tier more generous

## Architecture
- Frontend: Vercel (serverless)
- Backend: Supabase + Vercel Functions
- Build: Vite for static, Next.js for SSR

## Key Learnings
1. Vercel's build cache significantly improved deploy times
2. Environment variables needed careful management across preview/production
3. Edge functions cold starts still an issue

## Configuration
```json
// vercel.json
{
  "buildCommand": "npm run build",
  "outputDirectory": "dist",
  "framework": "vite"
}
```
