# SYSTEM GUIDE — BRAIN AI Solutions Website

**Purpose of this document**  
This is the single source of truth for how the website is designed, structured, and should be maintained.  
It exists so both humans and future LLMs can quickly understand the overall system, the design decisions, the architecture, and how to safely extend or modify the project.

Read this first before making any significant change.

---

## 1. Project Overview

**What this is**  
A high-performance marketing website for **BRAIN AI Solutions** — an AI Operations company that sells business outcomes (capacity, clearer decisions, growth) through reusable AI agents and managed services.

**Core experience**  
A long-scroll storytelling homepage with a clear emotional rhythm:

1. Hero (strong FOMO + promise)
2. The Shift (Before → After)
3. What becomes possible (Outcomes)
4. Real work examples
5. Understand the costs (educational / trust)
6. Packages
7. Who this is for
8. How we work
9. Final invitation

**Visual language**  
"White AI Lab": majority white / very light surfaces, electric blue as the only strong accent, generous whitespace, premium and calm.

---

## 2. Rendering Strategy (SSG vs SSR)

**Decision: Static Site Generation (SSG) with selective Client Components.**

### Why SSG?

- The homepage is almost entirely static content.
- We want maximum performance, SEO, and low hosting cost.
- No user-specific data or real-time personalization is required on the first version.
- Perfect for a marketing site that rarely changes.

### How we implement it in Next.js

- App Router + default static generation.
- Most components are Server Components.
- Only interactive / animated parts become Client Components (`"use client"`):
  - GSAP scroll animations
  - Navbar mobile menu
  - Any hover micro-interactions that need JS

### Future flexibility

If we later add a contact form with server actions, a blog, or a calculator, we can introduce SSR or dynamic routes only where needed. The rest of the site stays static.

**Recommendation confirmed:** SSG first. Do not force SSR unless there is a clear reason.

---

## 3. Technology Stack (approved versions)

We use industry-standard, stable, widely adopted versions.

| Layer              | Technology              | Recommended Version     | Notes |
|--------------------|-------------------------|-------------------------|-------|
| Framework          | Next.js (App Router)    | 15.x (or latest stable) | App Router only |
| Language           | TypeScript              | 5.x                     | `strict: true` |
| Styling            | Tailwind CSS            | 3.4+ / 4.x              | Prefer stable |
| Animation primary  | GSAP + ScrollTrigger    | latest stable           | Main storytelling animations |
| Animation secondary| Motion (`motion`)       | latest stable           | Small React UI states |
| Fonts              | Inter (via `next/font`) | —                       | Geometric sans |
| Icons              | Inline SVG              | —                       | From `/public/icons` |
| Images             | `next/image`            | —                       | Prefer WebP |
| Package manager    | pnpm or npm             | —                       | Prefer lockfile |
| Hosting            | Vercel (recommended)    | —                       | Or any static host |

### Security & dependency principles

- Prefer well-maintained packages with large communities.
- Pin major versions when possible.
- Avoid unnecessary dependencies.
- Follow OWASP Top 10 awareness (especially for any future forms or APIs):
  - No sensitive data in client-side code
  - Proper input validation if forms appear
  - CSP-friendly setup
  - Secure headers (via `next.config`)
- Review dependency updates before applying them.

---

## 4. Responsive Strategy (Mobile-First — Mandatory)

**This website must be 100% responsive.**  
We design and implement **mobile-first**. This is not optional.

### Why mobile-first?

- Designing for the smallest screen first forces clarity, hierarchy and prioritization.
- It is significantly harder to make a desktop design work well on mobile than the opposite.
- Mobile traffic is dominant for most marketing sites.
- It produces cleaner, more maintainable CSS.

### Professional approach we use

1. **Write base styles for mobile** (0–767px).
2. **Then enhance progressively** with Tailwind breakpoints:
   - `sm:` → 640px+
   - `md:` → 768px+ (tablet)
   - `lg:` → 1024px+ (desktop)
   - `xl:` → 1280px+
   - `2xl:` → 1536px+

3. **Layout principles:**
   - Stack everything vertically by default.
   - Use CSS Grid / Flexbox with responsive utilities.
   - Prefer `gap` over margins for spacing consistency.
   - Images and cards must reflow cleanly.
   - Touch targets ≥ 44px on mobile.
   - Avoid horizontal scroll at all costs.

4. **Component responsibility:**
   - Every section component must look correct on mobile, tablet and desktop.
   - Shared UI components (`Button`, `Card`, `SectionHeader`) are built mobile-first from the start.

5. **Testing expectation:**
   - Always check mobile width first during development.
   - Use browser DevTools + real device when possible.
   - Never consider a section "done" until it works well on mobile.

### Tailwind convention we follow

```tsx
// ✅ Correct (mobile-first)
<div className="flex flex-col gap-6 md:flex-row md:gap-10 lg:gap-16">

// ❌ Avoid (desktop-first thinking)
<div className="flex flex-row gap-16 max-md:flex-col max-md:gap-6">
```

### Breakpoints reference (from Design Foundations)

| Name    | Width        |
|---------|--------------|
| Mobile  | 0 – 767 px   |
| Tablet  | 768 – 1023 px|
| Desktop | 1024 px +    |
| Wide    | 1280 px +    |

---

## 5. High-level Architecture

```
Marketing Website (SSG)
│
├── Public assets
│   ├── brand/          (logos, favicons, og-image)
│   ├── icons/          (36 line icons)
│   └── images/         (hero, shift, outcomes, scenes...)
│
├── Content source of truth
│   └── website/content/homepage-copy.md
│
├── Design system
│   └── website/design/design-foundations.md
│
├── Code
│   ├── app/            (Next.js App Router)
│   ├── components/
│   │   ├── layout/     (Navbar, Footer)
│   │   ├── sections/   (one component per homepage section)
│   │   ├── ui/         (Button, Card, SectionHeader...)
│   │   └── animation/  (GSAP helpers)
│   └── lib/            (tokens, gsap setup, constants)
│
└── This guide
```

**Key principle:**  
Each homepage section = one clear React component.  
Shared UI pieces live in `ui/`.  
Animation logic is centralized as much as possible.

---

## 6. Component & Section Strategy

| Section                    | Component name              | Notes |
|---------------------------|-----------------------------|-------|
| Hero                      | `Hero.tsx`                  | Strong entrance animation |
| The Shift                 | `TheShift.tsx`              | Before/After comparison |
| What becomes possible     | `WhatBecomesPossible.tsx`   | 3 outcome cards |
| FOMO Quote                | `FomoQuote.tsx`             | Reusable interstitial |
| Real work examples        | `RealWorkExamples.tsx`      | Scene cards |
| Understand the costs      | `UnderstandCosts.tsx`       | Educational + tables |
| Packages                  | `Packages.tsx`              | 3 package cards |
| Who this is for           | `WhoThisIsFor.tsx`          | Industries |
| How we work               | `HowWeWork.tsx`             | 5 process steps |
| Final invitation          | `FinalInvitation.tsx`       | Closing CTA |

Shared UI components follow Design Foundations (`Button`, `SectionHeader`, `Card`, etc.).

All of them must be built **mobile-first**.

---

## 7. Animation Approach

- **Primary:** GSAP + ScrollTrigger for scroll-driven storytelling.
- **Secondary:** Motion for small React state animations when simpler.
- Always respect `prefers-reduced-motion`.
- Prefer subtle fade + slight translate / soft scale.
- Staggered reveals for cards.
- Duration mostly 0.4–0.9s with soft eases.

Priority animation moments are defined in `design-foundations.md` and `stack-and-structure.md`.

---

## 8. How to extend the system safely

When adding something new:

1. Check this guide + Design Foundations first.
2. Decide if it is content, visual asset, or code component.
3. Place it in the correct location (see section 9 below).
4. Prefer reusing existing UI components.
5. Keep the visual language consistent (White AI Lab).
6. **Always implement mobile-first.**
7. Update this document if the architecture changes.

---

## 9. Source of Truth Separation

This section is deliberately separated so anyone (human or LLM) can quickly know **where to look** for each type of information.

### A. Content / Text / Data

All textual content used on the homepage lives here:

| What                              | Location                                      |
|-----------------------------------|-----------------------------------------------|
| Final homepage copy (all sections)| `website/content/homepage-copy.md`            |
| FOMO quotes                       | `website/design/fomo-quotes.md`               |
| Design tokens & rules             | `website/design/design-foundations.md`        |
| Marketing plan & story structure  | `website/design/00-plan.md`                   |

**Rule:** Do not hardcode long marketing copy inside components if it already exists in the content files. Prefer importing or keeping a single source of truth.

---

### B. Visual Assets & Media

| Type                    | Location (future code)              | Current working location                  |
|-------------------------|-------------------------------------|-------------------------------------------|
| Logos & brand           | `/public/brand/`                    | `website-assets/public/brand/`            |
| Line icons (SVG)        | `/public/icons/`                    | `website-assets/public/icons/`            |
| Hero images             | `/public/images/hero/`              | `website-assets/public/images/hero/`      |
| The Shift               | `/public/images/shift/`             | `website-assets/public/images/shift/`     |
| Outcomes                | `/public/images/outcomes/`          | `website-assets/public/images/outcomes/`  |
| Real work scenes        | `/public/images/scenes/`            | (pending)                                 |
| Cost diagrams           | `/public/images/costs/`             | (pending)                                 |
| Favicons & OG           | `/public/brand/` + root             | already prepared                          |

**Asset rules:**
- Prefer SVG for icons and logos.
- Prefer WebP for photographic / illustrative images when possible.
- Use `next/image` for performance and sizing.
- Keep filenames exactly as defined in `assets-for-code.md`.

---

### C. System Design, Architecture & Dependencies

This is the technical layer.

**Key documents:**
- This file (`SYSTEM-GUIDE.md`)
- `website/tech/stack-and-structure.md`
- `website/design/design-foundations.md`

**Machine-readable snapshot of the stack (for tools / future automation):**

```yaml
project:
  name: brain-ai-solutions-website
  type: marketing-site
  rendering: SSG
  framework: nextjs-app-router
  responsive: mobile-first   # mandatory

stack:
  nextjs: "15.x"
  react: "19.x"
  typescript: "5.x"
  tailwindcss: "3.4+ or 4.x"
  gsap: "latest-stable"
  motion: "latest-stable"
  font: "Inter via next/font"

architecture:
  style: component-based
  sections: one-component-per-section
  responsive_strategy: mobile-first
  animation:
    primary: gsap-scrolltrigger
    secondary: motion
  assets:
    icons: inline-svg
    images: next-image + webp

security:
  approach: owasp-aware
  principles:
    - minimal-dependencies
    - no-secrets-in-client
    - validate-any-future-forms
    - secure-headers

deployment:
  preferred: vercel
  alternative: any-static-host
```

---

## 10. Current Status (as of document creation)

- Design Foundations ✅
- Homepage copy ✅
- Tech stack decision ✅
- Brand assets + icon library ✅
- Hero brain assets ✅
- The Shift asset ✅
- Outcomes assets ✅
- Real work scenes ⏳ (pending generation)
- Cost diagrams ⏳
- Code implementation → starting now

---

## 11. Next Steps

1. Finalize this guide and get explicit approval.
2. Create a **new dedicated repository** for the actual website code.
3. Scaffold Next.js + TypeScript + Tailwind with the approved versions.
4. Implement design tokens + mobile-first base styles.
5. Build Hero + The Shift first (with placeholders if needed).
6. Continue section by section, always validating mobile first.

---

**This document should be updated whenever a significant architectural or structural decision is made.**
