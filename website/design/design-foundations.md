# Design Foundations — BRAIN AI Solutions

This document is the single source of truth for visual and interaction rules.  
Everything we build later (content, assets, and code) must follow these foundations.

---

## 1. Brand & Visual Direction

**Name:** BRAIN AI Solutions  
**Feeling:** Clean, premium, calm, futuristic, trustworthy (White AI Lab)  
**Tone:** Clear, adult, slightly urgent but never aggressive

**Core visual principles**
- Majority white / very light surfaces
- Electric blue as the only strong accent
- Generous whitespace
- Short text blocks
- Strong hierarchy
- Recurring “legos”: quote blocks, outcome cards, scene cards, clean tables

---

## 2. Color System

### Primary
| Token | Value | Usage |
|-------|-------|-------|
| `--color-primary` | `#0066FF` | Main CTAs, key accents |
| `--color-primary-soft` | `#00A3FF` | Gradients, highlights, icon accents |
| `--color-primary-dark` | `#0052CC` | Hover states |

### Neutrals
| Token | Value | Usage |
|-------|-------|-------|
| `--color-navy` | `#0A1628` | Headlines, strong text |
| `--color-text` | `#0F172A` | Body text |
| `--color-text-muted` | `#64748B` | Secondary text, captions |
| `--color-border` | `#E2E8F0` | Dividers, card borders |
| `--color-bg` | `#FFFFFF` | Main background |
| `--color-bg-soft` | `#F8FAFC` | Alternate sections, cards |
| `--color-bg-tint` | `#F0F7FF` | Very light blue tint sections |

### Semantic (optional later)
- Success: `#10B981`
- Warning: `#F59E0B`
- Error: `#EF4444`

**Rule:** Almost no other colors. Blue + navy + whites/grays only.

---

## 3. Typography

**Font family:** Modern geometric sans-serif  
Recommended: `Inter`, `SF Pro`, or `Plus Jakarta Sans`

### Scale (Desktop)
| Token | Size | Weight | Line height | Usage |
|-------|------|--------|-------------|-------|
| `--text-hero` | 48–64 px | 700 | 1.1 | Hero headline |
| `--text-h1` | 40–48 px | 700 | 1.15 | Section titles |
| `--text-h2` | 28–32 px | 600 | 1.2 | Sub-sections |
| `--text-h3` | 20–24 px | 600 | 1.3 | Card titles |
| `--text-body` | 16–18 px | 400 | 1.6 | Body |
| `--text-small` | 14 px | 400 | 1.5 | Captions, labels |
| `--text-quote` | 24–32 px | 500–600 | 1.3 | FOMO quotes |

### Mobile adjustments
- Hero: ~32–40 px
- H1: ~28–32 px
- Body stays 16 px minimum

**Rules**
- Never use serif
- Headlines can be tight; body needs comfortable line-height
- FOMO quotes should feel editorial and strong

---

## 4. Spacing & Layout

### Spacing scale (8-point)
`4, 8, 12, 16, 24, 32, 48, 64, 80, 96, 128`

### Section padding (vertical)
| Breakpoint | Padding |
|------------|--------|
| Mobile | 64–80 px |
| Tablet | 80–96 px |
| Desktop | 96–128 px |

### Container
- Max width: `1200px` (content) / `1280px` absolute
- Side padding: 20–24 px (mobile) → 32–48 px (desktop)

### Grid
- 12-column mental model on desktop
- Common patterns:
  - Full-width statement
  - 50 / 50 split
  - 3-column cards
  - 2-column scenes

---

## 5. Responsive Breakpoints

| Name | Width |
|------|-------|
| Mobile | 0 – 767 px |
| Tablet | 768 – 1023 px |
| Desktop | 1024 px + |
| Wide | 1280 px + |

**Responsive principles**
- Mobile first
- Stack everything cleanly on mobile
- Hero: brain above text on mobile, side-by-side on desktop
- Cards go from 3 → 2 → 1 column
- Tables on mobile become stacked cards or horizontal scroll (prefer stacked)
- FOMO quotes remain full-width and powerful at every size

---

## 6. Core Components (“Legos”)

These are the reusable building blocks used across sections.

### 6.1 Buttons
- **Primary:** solid blue, white text, rounded-lg, medium padding
- **Secondary:** white / soft border, navy text
- **Tertiary / text:** blue text + arrow
- States: default, hover, active, disabled
- Min height ~44 px (touch friendly)

### 6.2 FOMO Quote Block
- Full-width or centered
- Large typography (`--text-quote`)
- Optional thin blue line accent
- Lots of whitespace above/below
- No heavy illustration

### 6.3 Outcome / Feature Card
- Soft white or tinted background
- Light border or very soft shadow
- Icon (32 px) + title + one short sentence
- Equal height in a row

### 6.4 Scene Card (Real work examples)
- Image / illustration on top or left
- Short label + one outcome line
- Clean, almost editorial

### 6.5 Package Card
- Clear hierarchy: name → who it’s for → 3 bullets → soft CTA
- Optional small price
- One card can be visually highlighted (recommended plan)

### 6.6 Simple Table (Costs section)
- Clean header
- Soft zebra or very light borders
- Mobile: transform into stacked definition lists or cards

### 6.7 Section Header
- Small optional eyebrow
- Strong H2
- One short supporting sentence (max)
- Optional thin blue accent line

### 6.8 Navigation
- Logo left
- Links center/right
- Primary CTA right
- Mobile: logo + hamburger
- Sticky optional (clean, light)

---

## 7. Iconography

- Style: geometric line icons
- Stroke: 1.5–2 px
- Color: primary blue or navy
- Sizes: 24 px (UI) and 32 px (cards)
- Prefer SVG, inline when critical

See full list in `assets-for-code.md`.

---

## 8. Illustration & Photography Style

- Prefer soft 3D / clean abstract tech visuals over stock photos
- Floating brain, light nodes, soft glows, minimal platforms
- Avoid dark cyberpunk
- Avoid busy collages
- Real-work scenes should feel calm and aspirational, not chaotic

---

## 9. Motion

**Primary library:** GSAP (+ ScrollTrigger)  
**Complement:** Motion (Framer Motion family) for small React UI state animations when useful

### Principles
- Subtle, purposeful, premium
- Prefer fade + slight translate (8–20 px) or soft scale
- Staggered reveals for cards and lists
- Scroll-triggered section entrances and FOMO quotes
- Duration mostly 0.4–0.9s
- Soft eases (power2 / power3)
- Always respect `prefers-reduced-motion`
- No constant heavy parallax or distracting loops

### Priority animated moments
1. Hero entrance
2. The Shift (Before → After)
3. Outcome cards stagger
4. FOMO quote interstitials
5. Real-work scenes
6. Cost scenarios / tables
7. Package cards
8. Final invitation

---

## 10. Content Rules (linked to design)

- Headlines: short and strong
- Body: maximum 2–3 short lines when possible
- One idea per card
- FOMO quotes stand alone
- Prefer showing over long explaining

---

## 11. Accessibility baseline

- Contrast: navy/blue on white must pass WCAG AA
- Focus states visible on all interactive elements
- Touch targets ≥ 44 px
- Meaningful alt text on important images
- Semantic headings in order
- Honor reduced motion preferences

---

## 12. How we use this document

1. Write final content per section following hierarchy rules here
2. Generate visual assets following `assets-for-code.md`
3. Implement components exactly as defined in this foundations file
4. Any new component must be added here before being used widely

---

## Next steps after this file

1. Final copy for every section ✅
2. Generate the visual assets
3. Development (Next.js + Tailwind + GSAP)
