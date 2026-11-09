# HANDOFF — BRAIN AI Solutions

**For future Grok sessions:** this is the single entry point.  
Read this first, then follow the linked files. The user will mainly share this repo link as context.

---

## What this project is

We are building **BRAIN AI Solutions** — an AI Operations company for SMEs and small professionals.

**Positioning:** AI Operations Partner (not a chatbot vendor).  
**Tagline:** Smarter Business. Powered by AI.  
**Sub:** Integrate. Automate. Grow.

We sell outcomes (hours saved, capacity, faster response, clearer operations) through reusable AI agents + integrations, packaged as managed monthly services.

**Repo:** `Omitofo/ai-solutions-blueprint` (private)

---

## Current phase

We are in **pre-development / design completion** for the company website.

Order of work we agreed:

1. Design Foundations ✅
2. Final homepage copy ✅
3. Assets specification ✅
4. Technical structure + animation stack ✅
5. **Generate visual assets** ⏳ (blocked by image generation limit)
6. **Implement the website in code** → next after assets (or in parallel with placeholders)

---

## What is already done (do not redo)

### Strategy & business blueprint
- Vision, packages, cost model, architecture direction, roadmap, industries, automation catalogue
- Location: `/docs/`

### Website content & design system
| File | Purpose |
|------|--------|
| `website/design/00-plan.md` | Scroll story + FOMO rhythm + marketing philosophy |
| `website/design/design-foundations.md` | Colors, type, spacing, components, responsive, motion rules |
| `website/design/assets-for-code.md` | **Single source of truth for all visual assets** (names, formats, sizes, folders) |
| `website/design/fomo-quotes.md` | FOMO quote bank |
| `website/content/homepage-copy.md` | **Final copy** for every homepage section |
| `website/tech/stack-and-structure.md` | Next.js + Tailwind + GSAP (+ Motion) + folder structure |

### Key product decisions already locked
- **Hero FOMO is inside the Hero** (not a separate first section):
  - Headline: `Smarter Business. Powered by AI.`
  - FOMO line: `Don’t get left behind. Integrate and ride the wave of the future.`
  - No extra supporting paragraph in Hero (kept intentionally lean)
- Emotional rhythm: FOMO in Hero → lift → soft FOMO quote interstitials every 2–3 sections
- Strong educational section on **tokens & costs** (transparency as marketing)
- Packages: Office Assistant / Business Operations / Business Infrastructure
- Visual style: **White AI Lab** (majority white, electric blue accents, clean, premium, not dark cyberpunk)
- Animation: **GSAP + ScrollTrigger primary**, Motion as complement for small React UI states

---

## What is missing

### 1. Visual assets (blocked right now)
Image generation limit was hit. When available again, generate **one by one** following priority in `website/design/assets-for-code.md`:

1. Logo (horizontal + icon)
2. Hero brain (`hero-brain-desktop` / `hero-brain-mobile`)
3. The Shift before/after visual
4. Outcome icons/cards
5. Real-work scene illustrations
6. Cost diagrams
7. Remaining icons + industry/package support visuals
8. OG image + favicon

Save generated assets following the paths defined in `assets-for-code.md`.
Local working folder already started conceptually under project artifacts as `website-assets/public/...` mirroring the future codebase.

### 2. Website code
Not started yet.

Stack decided:
- Next.js (App Router)
- TypeScript
- Tailwind CSS
- GSAP + ScrollTrigger
- Motion (optional complement)
- Inter (or similar geometric sans)

Implementation order is already written in `website/tech/stack-and-structure.md`.

### 3. Optional polish later
- Secondary pages (Solutions detail, Catalogue, etc.)
- Real contact form / booking
- Business-case calculator (Excel or web tool) from earlier strategy docs

---

## What the next session should do

### If image generation works again
1. Open `website/design/assets-for-code.md`
2. Generate the next missing asset in priority order (start with Hero brain if not done)
3. Save it with the exact filename and folder convention
4. Continue one asset at a time
5. Do not regenerate strategy/copy unless the user asks

### If starting code
1. Scaffold Next.js + Tailwind + TypeScript
2. Apply design tokens from `design-foundations.md`
3. Build section components using `homepage-copy.md`
4. Use placeholder images until real assets exist
5. Wire GSAP for the priority animation moments listed in the foundations/tech docs

### If the user only says “continue”
Default path:
1. Check whether images can be generated
2. If yes → produce next asset(s)
3. If no → offer to start coding with placeholders or refine anything they want

---

## Important tone / marketing rules (do not drift)

- Sell the carrot (better future state), not feature lists
- FOMO is intentional but **not mean** — inspirational urgency
- Teach (especially costs/tokens) to build trust and authority
- Short text, strong structure, lots of whitespace
- Show more than talk
- Responsive from the start
- Premium, calm, adult — never hypey or chaotic

---

## Quick file map

```
/
├── HANDOFF.md                      ← you are here
├── README.md
├── docs/                           ← business blueprint
├── website/
│   ├── content/homepage-copy.md    ← final text
│   ├── design/
│   │   ├── 00-plan.md
│   │   ├── design-foundations.md
│   │   ├── assets-for-code.md      ← asset production guide
│   │   └── fomo-quotes.md
│   └── tech/stack-and-structure.md
├── brainstorm/
└── templates/
```

---

## User context (short)

- Software developer building his own AI solutions company
- Target: SMEs / professionals / individuals (Spain/Europe focus in strategy)
- Conversation language: Spanish mixed with English technical terms
- Prefers clear structure, section-by-section work, and not cramming everything into one image/mockup
- Brand assets exist (logo + brand board) from earlier messages; logo treatment: **BRAIN** with **AI** in brighter blue, smaller “AI solutions” below

---

## One-sentence status

**Strategy, copy, design system, asset list, and tech plan are ready. Next: generate visuals when possible, then build the Next.js site with GSAP.**

Sleep well. Continue from here.
