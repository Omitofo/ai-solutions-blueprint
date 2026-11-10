# website-assets

Visual assets for the BRAIN AI Solutions website. `public/` mirrors the folder that will be copied into the Next.js project (`/public`), so paths stay identical between this repo and the codebase.

**Specs and naming:** `website/design/assets-for-code.md` (source of truth).
**Progress:** `website/design/ASSETS-PROGRESS.md`.
**Prompts for raster images:** `website/design/image-prompts.md`.

## Structure

```
website-assets/
├── public/
│   ├── brand/      logo (SVG + PNG, colour / white / mono), favicons, apple-touch, og-image
│   ├── icons/      36 SVG line icons (24px grid, 1.75 stroke, currentColor)
│   └── images/     hero, shift, scenes, costs … (raster, WebP – to be added)
└── reference/      mood references and the original logo source (not shipped)
```

## Using the icons

Icons use `stroke="currentColor"`, so colour them with CSS/Tailwind (`text-primary`, `text-navy`). They carry `aria-hidden="true"`; if an icon is the only content of a control, add an accessible label to the control.

```tsx
<span className="text-primary [&>svg]:size-8">{/* inline the SVG */}</span>
```

Naming: `icon-<name>.svg`; process steps `icon-step-*`; industries `icon-industry-*`.

## Using the logo

| File | When |
|------|------|
| `logo-horizontal.svg` | Navbar, footer on light backgrounds |
| `logo-horizontal-white.svg` | Dark or blue backgrounds |
| `logo-horizontal-mono.svg` | Single-colour print / stamps |
| `logo-icon.svg` | Mobile nav, avatars |
| `favicon.svg`, `favicon-32.png`, `favicon-16.png`, `apple-touch-icon.png`, `icon-512.png` | Metadata / PWA |
| `og-image.png` (1200×630) | Social sharing |

The SVG logos are traced from `reference/logo-source.png`. Keep clear space equal to the height of the "A" around the logo, and do not recolour the gradient.

## Rules

- Palette only from `design-foundations.md` (blue `#0066FF → #00A3FF`, navy `#0A1628`, whites/greys).
- Raster images: WebP, hero < 250 KB, with meaningful `alt` text (or empty alt if decorative).
- Do not commit secrets, API keys or unoptimised originals.
