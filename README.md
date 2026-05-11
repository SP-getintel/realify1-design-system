# Realify Design System

A living style guide for **Realify** — AI appointment setting for Australian real estate agents.
Source of truth: the production codebase at `SP-getintel/realify1` (React 19 + TanStack Start + Tailwind v4 + shadcn/ui "new-york").

---

## Brand at a glance

- **Product**: Realify installs an AI system that reactivates databases, responds to enquiries instantly, and books qualified appointments straight into agents' calendars.
- **Audience**: Australian real-estate agents and sales teams.
- **Voice**: Confident, plain-spoken, outcome-led. Skip jargon. Talk about leads, listings, appointments, and dollars.
- **Owner**: Imminent Intelligence Pty Ltd.

---

## Foundations

### Colors

The palette is two-tone by design: a deep **navy** carries authority and contrast surfaces; a single **amber** accent owns every call-to-action, focus state, and conversion moment. Everything else is a neutral derived from the navy hue so the surface always feels cool, never gray-dead.

| Token | OKLCH | Hex (approx) | Use |
|---|---|---|---|
| `--primary` | `oklch(0.22 0.05 250)` | `#0A2440` | Brand navy. Hero, footer, sidebar, primary buttons. |
| `--amber` | `oklch(0.75 0.18 75)` | `#F59E0B` | Single CTA color. Never two ambers in one frame. |
| `--navy-light` | `oklch(0.30 0.05 250)` | `#16335A` | Hover/elevated navy, sidebar accents. |
| `--background` | `oklch(1 0 0)` | `#FFFFFF` | Page surface. |
| `--foreground` | `oklch(0.22 0.05 250)` | `#0A2440` | Default text — same as primary. |
| `--card` | `oklch(0.97 0.005 250)` | `#F4F6F9` | Card surface on white. |
| `--muted` | `oklch(0.95 0.01 250)` | `#EEF1F5` | Subtle fills, skeleton bg. |
| `--muted-foreground` | `oklch(0.45 0.03 250)` | `#5E6B7E` | Captions, helper text. |
| `--border` / `--input` | `oklch(0.90 0.01 250)` | `#DCE1E8` | Hairlines. |
| `--ring` | `oklch(0.75 0.18 75)` | `#F59E0B` | Focus ring = amber. |
| `--destructive` | `oklch(0.577 0.245 27.325)` | `#DC2626` | Errors only. |

**Rules**
- Body copy is `--foreground` (navy), not black. Pure black is reserved for image overlays.
- Amber pairs with navy or white only — never on `--muted` or `--card`.
- Charts cycle `--chart-1…5`: amber, mid-blue, deep-navy, warm-yellow, soft-blue.

### Typography

| Role | Family | Notes |
|---|---|---|
| Heading | **Manrope** | 700–800 weight. Tight tracking. Use for h1–h6, navbar logo wordmark, badges. |
| Body | **Inter** | 400–500 weight. Default for everything else. |

Heroes use `text-[2rem]` on mobile climbing to `text-6xl` on desktop with `leading-[1.15]`. Eyebrow labels are `text-xs sm:text-sm font-semibold uppercase tracking-wide` in amber.

### Spacing & radii

- Radius scale derives from `--radius: 0.75rem` — `sm` (8px), `md` (10px), `lg` (12px), `xl` (16px), `2xl` (20px).
- Default card radius is `rounded-xl`. Dashboard imagery uses `rounded-2xl` with a soft amber glow.
- Section vertical rhythm: `py-14 sm:py-20 md:py-28` on landing sections; `pt-32 pb-14` on the hero (to clear the fixed 80px navbar).

---

## Components

All components come from **shadcn/ui (`new-york` style)** over Radix primitives. Icons are **lucide-react**. Two custom button variants extend the base set:

- `variant="hero"` — amber fill, navy text, `shadow-lg`, `font-semibold`. The primary conversion CTA across the marketing site.
- `variant="heroOutline"` — 2px amber border on transparent, amber text, fills on hover. Used as the secondary CTA next to `hero`.

The base palette of variants (`default`, `destructive`, `outline`, `secondary`, `ghost`, `link`) is otherwise unchanged from shadcn.

See the component cards in this design system for live examples.

---

## Imagery & iconography

- **Logo**: house silhouette + amber upward arrow + wordmark "Realify" in Manrope-bold navy. Always lockup; never split the mark from the wordmark in product surfaces. On dark backgrounds use the inverted (white) version (`brightness-0 invert`).
- **Australia silhouette**: used to signal "Australia-only" status, agent geography, or coverage. Rendered via CSS mask so it inherits `currentColor`.
- **Photography**: Real Australian agents, listings, and landscapes. No stock-people clichés. Image cards in the feature grid (`feature-amplify`, `feature-convert`, `feature-nurture`, `feature-reactivate`) are 4:3, lightly tinted to read against navy backdrops.

---

## Tech stack (reference)

React 19, TanStack Start (file-based routing + SSR), Tailwind v4 with `@theme inline` tokens, Supabase (Postgres + Auth + Edge Functions), Cloudflare Workers via Vite. UI built with shadcn/ui `new-york`, Radix UI, lucide icons, framer-motion for hero animation, recharts for portal analytics.
