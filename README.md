# Aris Homes

**Tagline:** Find your vibe, not just a house.

Aris Homes is a premium, AI-powered real estate web application built with Next.js 15, TypeScript, Tailwind CSS, shadcn-style components, Supabase, Vercel AI SDK, Mapbox GL JS, Zustand, TanStack Query, React Hook Form, Zod, Framer Motion, and PWA support.

## What is implemented

- Dark-mode-first luxury UI and responsive shell
- Home / Vibe Feed (`/`)
- Natural-language search (`/search`)
- TikTok-style vertical matches feed (`/matches`)
- Premium property detail page (`/property/[id]`)
  - image gallery + lightbox
  - AI virtual staging toggle
  - AI-generated description
  - AI valuation, confidence, trend, comps
  - visual vibe radar chart
  - chat/save/share/viewing CTAs
- Seller Listing Studio (`/listing-studio`)
- Floating Aris AI Concierge
- Mapbox-ready map page (`/map`) with fallback when token is missing
- Buyer/Seller/Agent dashboard shell (`/dashboard`)
- Supabase schema migration with PostGIS and RLS
- API routes for properties, AI chat, AI search, listing studio, and webhooks
- PWA manifest and service worker
- Multi-agent coordination plan in `AGENTS.md`

## Quick start

```bash
cd aris-homes
npm install
cp .env.example .env.local
npm run dev
```

Open <http://localhost:3000>.

## Environment variables

```bash
NEXT_PUBLIC_SUPABASE_URL=
NEXT_PUBLIC_SUPABASE_ANON_KEY=
SUPABASE_SERVICE_ROLE_KEY=
NEXT_PUBLIC_MAPBOX_TOKEN=
OPENAI_API_KEY=
ANTHROPIC_API_KEY=
NEXT_PUBLIC_APP_URL=http://localhost:3000
```

The app works in demo mode without env vars. Add keys to unlock Supabase persistence, live Mapbox maps, and model-backed AI output.

## Supabase setup

1. Create a Supabase project.
2. Enable Google auth provider if needed.
3. Run the migration in `supabase/migrations/202606200001_initial_schema.sql`.
4. Create a public `property-images` storage bucket.
5. Add storage upload policies when the real listing photo upload flow is connected.

## Scripts

```bash
npm run dev        # local development
npm run typecheck  # TypeScript validation
npm run build      # production build
npm run start      # run production build
```

## Validation

Current checkpoint validation:

- `npm run typecheck` passes
- `npm run build` passes on Next.js 15.5.19

## Project structure

```text
aris-homes/
├── app/
│   ├── (auth)/
│   ├── (main)/
│   │   ├── page.tsx
│   │   ├── search/
│   │   ├── property/[id]/
│   │   ├── matches/
│   │   ├── dashboard/
│   │   ├── listing-studio/
│   │   └── map/
│   ├── api/
│   │   ├── ai/
│   │   ├── properties/
│   │   └── webhooks/
│   ├── globals.css
│   └── layout.tsx
├── components/
├── lib/
├── hooks/
├── stores/
├── types/
├── public/
└── supabase/migrations/
```
