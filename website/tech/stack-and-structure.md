# Technical Stack & Project Structure

## Recommended Stack

**Framework:** Next.js (App Router)  
**Styling:** Tailwind CSS  
**Language:** TypeScript  
**Icons:** Inline SVG or a simple SVG sprite  
**Images:** Next.js `<Image>` with WebP  
**Fonts:** Inter (or Plus Jakarta Sans) via `next/font`  
**Deployment:** Vercel (simplest) or any Node host

Why this stack:
- Fast to build and iterate
- Excellent responsive + image handling
- Clean component model that matches our Design Foundations
- Easy to keep the site mostly static at the beginning

---

## High-level architecture

```
Marketing site (mostly static)
├── Homepage (long scroll story)
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
│   │   ├── logo-horizontal.svg
│   │   ├── logo-icon.svg
│   │   ├── favicon.svg
│   │   └── og-image.png
│   ├── images/
│   │   ├── hero/
│   │   ├── shift/
│   │   ├── outcomes/
│   │   ├── scenes/
│   │   ├── costs/
│   │   ├── packages/
│   │   └── industries/
│   └── icons/
│       ├── icon-email.svg
│       ├── icon-chart.svg
│       └── ...
├── src/
│   ├── app/
│   │   ├── layout.tsx
│   │   ├── page.tsx              ← Homepage
│   │   ├── globals.css
│   │   └── (optional secondary routes later)
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
│   │   └── icons/
│   └── lib/
│       └── constants.ts          ← copy, navigation links, etc.
└── tailwind.config.ts
└── package.json
```

---

## Component strategy

Each homepage section = one component in `components/sections/`.

Shared UI pieces live in `components/ui/` following Design Foundations:
- Button
- SectionHeader
- FomoQuote
- OutcomeCard
- PackageCard
- etc.

Copy can live in `lib/constants.ts` or in a simple CMS-less content file so it is easy to edit.

---

## Design tokens in code

Map the Design Foundations tokens directly into Tailwind:

```ts
// tailwind.config example direction
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
3. Navbar + Footer
4. Hero section (even with placeholder image)
5. The Shift
6. What becomes possible
7. FOMO quote component
8. Remaining sections one by one
9. Replace placeholders with real assets as they are generated
10. Polish responsive + accessibility

---

## Current status

- Design Foundations ✅
- Final copy ✅
- Assets specification ✅
- Technical structure (this file) ✅
- Image generation ⏳ (limit)
- Code implementation → next when you want to start
