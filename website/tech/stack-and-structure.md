# Technical Stack & Project Structure

## Recommended Stack

**Framework:** Next.js (App Router)  
**Styling:** Tailwind CSS  
**Language:** TypeScript  
**Animation (primary):** **GSAP** (+ ScrollTrigger)  
**Animation (complement):** **Motion** (Framer Motion / `motion`) when it is simpler for React component states  
**Icons:** Inline SVG or simple SVG sprite  
**Images:** Next.js `<Image>` with WebP  
**Fonts:** Inter (or Plus Jakarta Sans) via `next/font`  
**Deployment:** Vercel (simplest) or any Node host

### Why this animation setup

- **GSAP** → best for scroll-driven storytelling, timeline sequences, section reveals, FOMO quote entrances, hero motion, staggered cards. This matches our long-scroll emotional rhythm.
- **Motion** → useful for smaller React UI interactions (hover, mount/unmount, layout transitions, button micro-interactions) when GSAP would be overkill.

We lead with GSAP for the main page experience. We add Motion only where it makes component-level animation cleaner.

---

## Animation principles (aligned with Design Foundations)

- Subtle, purposeful, premium
- Prefer fade + slight translate / soft scale
- Staggered reveals for cards and lists
- ScrollTrigger for section entrances and FOMO quotes
- Respect `prefers-reduced-motion`
- No heavy constant parallax or distracting loops
- Duration mostly 0.4–0.9s, ease soft (power2/power3)

### Priority animated moments
1. Hero entrance (headline, FOMO line, CTA, brain visual)
2. The Shift (Before → After reveal)
3. Outcome cards stagger
4. FOMO quote interstitials (strong, clean entrance)
5. Real-work scene cards
6. Cost section tables / scenario cards
7. Package cards
8. Final invitation

---

## High-level architecture

```
Marketing site (mostly static)
├── Homepage (long scroll story + GSAP scroll animations)
├── Optional secondary pages later
└── Contact (form or Cal.com / mailto for now)
```

We start with a **single strong homepage**. Secondary pages only when needed.

---

## Proposed folder structure

```
/
├── public/
│   ├── brand/
│   ├── images/
│   └── icons/
├── src/
│   ├── app/
│   │   ├── layout.tsx
│   │   ├── page.tsx
│   │   └── globals.css
│   ├── components/
│   │   ├── layout/
│   │   │   ├── Navbar.tsx
│   │   │   └── Footer.tsx
│   │   ├── sections/
│   │   │   ├── Hero.tsx
│   │   │   ├── TheShift.tsx
│   │   │   ├── WhatBecomesPossible.tsx
│   │   │   ├── FomoQuote.tsx
│   │   │   ├── RealWorkExamples.tsx
│   │   │   ├── UnderstandCosts.tsx
│   │   │   ├── Packages.tsx
│   │   │   ├── WhoThisIsFor.tsx
│   │   │   ├── HowWeWork.tsx
│   │   │   └── FinalInvitation.tsx
│   │   ├── ui/
│   │   │   ├── Button.tsx
│   │   │   ├── SectionHeader.tsx
│   │   │   ├── Card.tsx
│   │   │   └── ...
│   │   ├── animation/           ← GSAP helpers / wrappers
│   │   │   ├── FadeIn.tsx
│   │   │   ├── StaggerChildren.tsx
│   │   │   └── useGsap.ts
│   │   └── icons/
│   └── lib/
│       ├── constants.ts
│       └── gsap.ts                 ← register plugins, defaults
└── tailwind.config.ts
└── package.json
```

---

## Component strategy

Each homepage section = one component in `components/sections/`.

Shared UI pieces live in `components/ui/` following Design Foundations.

Animation helpers live in `components/animation/` so we don’t repeat GSAP setup in every section.

---

## Design tokens in code

Map Design Foundations tokens into Tailwind:

```ts
colors: {
  primary: {
    DEFAULT: '#0066FF',
    soft: '#00A3FF',
    dark: '#0052CC',
  },
  navy: '#0A1628',
  muted: '#64748B',
  soft: '#F8FAFC',
  tint: '#F0F7FF',
}
```

Font: Inter via `next/font/google`.

---

## Implementation order (when we code)

1. Scaffold Next.js + Tailwind + TypeScript
2. Global styles + design tokens
3. Install & configure **GSAP + ScrollTrigger** (and Motion if needed)
4. Navbar + Footer
5. Hero section (with entrance animation)
6. The Shift
7. What becomes possible
8. FOMO quote component (scroll-triggered)
9. Remaining sections one by one
10. Replace placeholders with real assets
11. Polish responsive + accessibility + reduced-motion support

---

## Packages to install (animation)

```bash
npm install gsap
npm install motion          # optional complement (Framer Motion family)
```

GSAP ScrollTrigger is included with the main `gsap` package.

---

## Current status

- Design Foundations ✅
- Final copy ✅
- Assets specification ✅
- Technical structure + animation stack ✅
- Image generation ⏳
- Code implementation → next when you want to start
