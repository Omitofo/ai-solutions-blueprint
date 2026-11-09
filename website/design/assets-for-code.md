# Visual Assets Specification — For Code Integration

This file is the single source of truth for every visual asset the website needs.  
It is written so we can generate the assets and later drop them straight into the codebase.

---

## 1. Global conventions

### Naming
```
[section]-[descriptor]-[size/variant].ext

Examples:
hero-brain-desktop.webp
hero-brain-mobile.webp
icon-email-24.svg
shift-before-after.webp
quote-fomo-01.webp
```

### Formats

| Type | Format | Notes |
|------|--------|-------|
| Icons | **SVG** (preferred) + PNG fallback @1x/2x | Clean geometric line icons, electric blue |
| Illustrations / section visuals | **WebP** (primary) + PNG fallback | High quality, optimized |
| Photos / complex scenes | **WebP** | |
| Logo | **SVG** + PNG | |
| Favicon | SVG + PNG 32/16 | |
| Open Graph / Social | PNG or JPG 1200×630 | |

### Color tokens (for icons & accents)
- Primary blue: `#0066FF` → `#00A3FF` (gradient allowed)
- Dark navy text: `#0A1628` / `#0F172A`
- Soft background: `#F8FAFC` / pure white
- Muted text: `#64748B`

### Icon style
- Geometric line icons
- 1.5–2 px stroke
- Rounded caps/joins
- Consistent optical size
- Preferred sizes: 24 px and 32 px base

---

## 2. Brand assets

| ID | Filename | Format | Size / Notes | Usage |
|----|----------|--------|--------------|-------|
| G01 | `logo-horizontal.svg` | SVG | Full wordmark: icon + BRAIN (AI in blue) + “AI solutions” | Navbar, footer |
| G02 | `logo-icon.svg` | SVG | Circuit-brain only | Mobile nav, favicon source |
| G03 | `favicon.svg` + `favicon-32.png` | SVG + PNG | 32×32 / 16×16 | Browser tab |
| G04 | `og-image.png` | PNG | 1200×630 | Social sharing |

---

## 3. Section-by-section assets

### 01 — Hero

| ID | Filename | Format | Recommended size | Description |
|----|----------|--------|------------------|-------------|
| H01 | `hero-brain-desktop.webp` | WebP | 1200×900 or larger | Floating translucent blue brain on soft platform, white AI Lab background |
| H02 | `hero-brain-mobile.webp` | WebP | 800×800 | Same concept, optimized for stacked mobile layout |

### 02 — The Shift (Before / After)

| ID | Filename | Format | Size | Description |
|----|----------|--------|------|-------------|
| S01 | `shift-before-after.webp` | WebP | 1400×800 | Full 50/50 comparison visual |
| S02 | `shift-before-scene.webp` | WebP | 700×600 | Overloaded manual work (optional separate) |
| S03 | `shift-after-scene.webp` | WebP | 700×600 | Connected calm systems |

**Icons for this section (SVG):**
- `icon-email-overload.svg`
- `icon-papers.svg`
- `icon-agent-ready.svg`
- `icon-crm-connected.svg`
- `icon-report-ready.svg`
- `icon-system-sync.svg`

### 03 — What becomes possible

| ID | Filename | Format | Size | Description |
|----|----------|--------|------|-------------|
| P01 | `outcome-capacity.webp` | WebP | 600×400 | Card visual or background |
| P02 | `outcome-decisions.webp` | WebP | 600×400 | |
| P03 | `outcome-growth.webp` | WebP | 600×400 | |

**Icons (SVG 32px):**
- `icon-capacity.svg` (rising chart)
- `icon-insights.svg` (lightbulb / data)
- `icon-growth.svg` (rocket)

### 04 — How it looks in real work

| ID | Filename | Format | Size | Description |
|----|----------|--------|------|-------------|
| R01 | `scene-email.webp` | WebP | 800×500 | Email assistant scene |
| R02 | `scene-quotation.webp` | WebP | 800×500 | Quotation preparation |
| R03 | `scene-invoices.webp` | WebP | 800×500 | Invoice processing |
| R04 | `scene-report.webp` | WebP | 800×500 | Daily/weekly report |
| R05 | `scene-followup.webp` | WebP | 800×500 | Lead follow-up |

### 05 — Understand the costs (Educational)

| ID | Filename | Format | Size | Description |
|----|----------|--------|------|-------------|
| C01 | `diagram-what-is-token.webp` | WebP | 900×500 | Simple text → tokens → response diagram |
| C02 | `diagram-multistep.webp` | WebP | 900×500 | Why one task can consume tokens multiple times |
| C03 | `scenario-card-a.webp` | WebP | 500×300 | Light email volume (optional decorative) |
| C04 | `scenario-card-b.webp` | WebP | 500×300 | Heavy admin user |
| C05 | `scenario-card-c.webp` | WebP | 500×300 | Higher volume / multi-step |

**Note:** Most of this section will be pure HTML tables + short text. Visuals are supporting only.

### 06 — Packages

| ID | Filename | Format | Size | Description |
|----|----------|--------|------|-------------|
| K01 | `package-office.webp` | WebP | 500×320 | Optional card illustration |
| K02 | `package-operations.webp` | WebP | 500×320 | |
| K03 | `package-infrastructure.webp` | WebP | 500×320 | |

Mostly CSS cards. Illustrations optional.

### 07 — Who this is for

| ID | Filename | Format | Size | Description |
|----|----------|--------|------|-------------|
| I01–I08 | `industry-[name].webp` or icons | WebP / SVG | 400×300 or 48px icons | Real Estate, Construction, Accountancy, Legal, Wholesale, E-commerce, Tourism, Clinics |

### 08 — How we work

| ID | Filename | Format | Size | Description |
|----|----------|--------|------|-------------|
| M01 | `process-steps.webp` | WebP | 1200×400 | Optional full process visual |
| — | Step icons (SVG) | SVG | 32–40 px | Discover, Design, Implement, Measure, Manage |

### 09 — Final invitation

| ID | Filename | Format | Size | Description |
|----|----------|--------|------|-------------|
| F01 | `closing-visual.webp` | WebP | 1200×600 | Quiet, confident forward energy (optional) |

### FOMO Quote Interstitials

Mostly typography. Optional subtle background:

| ID | Filename | Format | Notes |
|----|----------|--------|-------|
| Q01 | `quote-bg-soft.webp` | WebP | Very subtle light gradient or abstract wave (optional) |

---

## 4. Shared Icon Library (SVG)

All icons should live in `/public/icons/` or `/assets/icons/`.

| Filename | Meaning |
|----------|--------|
| `icon-brain.svg` | AI / intelligence |
| `icon-email.svg` | Email |
| `icon-calendar.svg` | Calendar / scheduling |
| `icon-document.svg` | Documents / invoices |
| `icon-chart.svg` | Reports / capacity |
| `icon-rocket.svg` | Growth |
| `icon-lightbulb.svg` | Insights |
| `icon-shield.svg` | Security |
| `icon-puzzle.svg` | Integration |
| `icon-cloud.svg` | Cloud / systems |
| `icon-users.svg` | Team / people |
| `icon-check.svg` | Success |
| `icon-arrow-right.svg` | CTA arrows |
| `icon-wave.svg` | Optional FOMO / future motif |

---

## 5. Recommended folder structure in the codebase

```
/public
  /brand
    logo-horizontal.svg
    logo-icon.svg
    favicon.svg
    favicon-32.png
    og-image.png
  /images
    /hero
      hero-brain-desktop.webp
      hero-brain-mobile.webp
    /shift
      shift-before-after.webp
    /outcomes
      ...
    /scenes
      scene-email.webp
      ...
    /costs
      diagram-what-is-token.webp
      ...
    /packages
    /industries
  /icons
    icon-email.svg
    icon-chart.svg
    ...
```

---

## 6. Generation priority order

When we can generate images again, produce in this order:

1. Logo (G01, G02)
2. Hero brain (H01, H02)
3. The Shift before/after (S01)
4. Outcome icons + cards (P01–P03)
5. Real work scenes (R01–R05)
6. Cost diagrams (C01, C02)
7. Remaining icons
8. Industry + package supporting visuals
9. OG image + favicon

---

## 7. Notes for implementation

- Always serve WebP with PNG/JPG fallback where needed.
- Use `srcset` + sizes for hero and large scenes.
- Icons as inline SVG or `<img>` from the icons folder (prefer inline for critical UI icons).
- Keep file sizes aggressive: hero < 200–250 KB if possible, icons tiny.
- All decorative images should have meaningful `alt` text or empty alt if purely decorative.
