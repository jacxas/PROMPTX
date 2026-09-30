# AGENTS.md

## Project Overview

PROMPTX (aka MGX) — Next.js 14 App Router app that generates monetization prompts via Google Gemini AI. TypeScript + Tailwind CSS. No database; freemium limits are tracked in browser localStorage.

## Setup

- **Runtime:** Node 20+ (compose uses `node:20-slim`)
- **Install:** `npm install` (package-lock.json present)
- **Dev:** `npx next dev -H 0.0.0.0 -p 3000` (binds 0.0.0.0 for preview access)
- **No database** — all state is client-side (localStorage) or static (`data/prompts.ts`)

## Environment Variables

| Variable | Required at boot | Purpose |
|----------|-----------------|---------|
| `NEXT_PUBLIC_GEMINI_API_KEY` | No | Google Gemini API key for AI prompt generation. App boots without it; only the `/api/generate` endpoint fails without it. |
| `BASE44_PUBLIC_HOST_SUFFIX` | No (platform-injected) | Used by `next.config.js` `allowedDevOrigins` to permit the preview origin. |

PayPal is a hardcoded `paypal.me` link — no PayPal SDK or env vars are used in the code despite the README mentioning them.

## Verification

1. `docker compose -f docker-compose.base44.yml up -d --build`
2. Wait for healthcheck to pass (`docker compose ps`)
3. `curl -s http://localhost:3000` should return the landing page HTML
4. The AI generation feature (`POST /api/generate`) only works with a valid `NEXT_PUBLIC_GEMINI_API_KEY`

## Architecture Notes

- `app/page.tsx` — landing page with category selector → prompt grid → prompt generator modal
- `app/api/generate/route.ts` — single API route, calls `lib/gemini.ts`
- `lib/gemini.ts` — wraps `@google/generative-ai` SDK, uses `gemini-pro` model
- `lib/freemium.ts` — client-side usage tracking via localStorage (5 free prompts/day)
- `data/prompts.ts` — static prompt templates across categories
