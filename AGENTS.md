# Aris Homes Multi-Agent Work Plan

Use this file to coordinate parallel agent work without stepping on each other.

## Agent lanes

1. **Foundation Agent**
   - Owns Next.js app setup, folder structure, Tailwind/shadcn primitives, package health, PWA metadata.
   - Files: `app/layout.tsx`, `app/globals.css`, `components/ui/*`, config files.

2. **Data/Auth Agent**
   - Owns Supabase schema, RLS, auth actions, profile onboarding persistence, storage policies.
   - Files: `lib/supabase.ts`, `supabase/migrations/*`, `app/(auth)/*`.

3. **Discovery Agent**
   - Owns home feed, search, matches, vibe tags, saved searches, recommendation logic.
   - Files: `app/(main)/page.tsx`, `app/(main)/search/*`, `app/(main)/matches/*`, `components/vibe/*`, `stores/*`.

4. **Property Experience Agent**
   - Owns detail page, gallery/lightbox, staging toggle, valuation, comps, charts, CTAs.
   - Files: `app/(main)/property/[id]/*`, `components/property/*`.

5. **AI Agent**
   - Owns AI Concierge, Listing Studio, prompts, Vercel AI SDK integrations, guardrails.
   - Files: `lib/ai.ts`, `components/ai/*`, `app/api/ai/*`.

6. **Maps/Dashboard Agent**
   - Owns Mapbox map, clusters, heatmaps, dashboards and analytics UI.
   - Files: `components/map/*`, `app/(main)/map/*`, `app/(main)/dashboard/*`.

## Checkpoints completed

- [x] Next.js 15 + TypeScript + Tailwind project scaffold
- [x] Required project structure
- [x] shadcn-style UI primitives
- [x] Dark luxury design system
- [x] Supabase client helpers
- [x] PostGIS schema + RLS migration
- [x] Home / Vibe Feed
- [x] Natural language search UI
- [x] Property cards and premium detail page
- [x] AI virtual staging toggle UI
- [x] AI valuation and comps panel
- [x] Vibe radar chart
- [x] AI Concierge demo/API route
- [x] Seller Listing Studio demo/API route
- [x] Mapbox-ready map with no-token fallback
- [x] Buyer/Seller/Agent dashboard shell
- [x] PWA manifest + service worker
- [x] Production build passes

## Next suggested checkpoints

- [ ] Implement server actions for Supabase Auth magic-link and Google OAuth callbacks.
- [ ] Persist onboarding role/vibes to `profiles`.
- [ ] Replace mock properties with Supabase queries and TanStack Query mutations.
- [ ] Add Supabase Storage upload flow and image moderation/label extraction.
- [ ] Add saved searches with scheduled email alerts via Supabase Edge Functions.
- [ ] Add Mapbox clustering, draw-search, and PostGIS radius queries.
- [ ] Add Stripe/CRM webhooks if monetization or lead routing is needed.
