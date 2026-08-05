# OPEXMINDS DESIGN SYSTEM — POLISH REBUILD BRIEF
## Goal: Rival Linear, Stripe, and Vercel design system docs

## Your Mission
Rewrite `/home/ubuntu/opexminds-designsystem/index.html` to be visually stunning, deeply content-rich, and free of every "AI tell." The current version is decent but flat. This rebuild adds depth, motion, grain, scroll-reveal, layout variation, and 3 NEW sections (Installation, Changelog, Resources). Target: 90-130KB of premium design system documentation.

## CRITICAL DESIGN RULES (Follow ALL of these)

### 1. Strip AI Tells
- REMOVE "SCROLL TO EXPLORE ↓" from the hero. No scroll cues anywhere.
- REMOVE section-number eyebrows (01, 02, 03...) from section headers. Use plain labels instead.
- REMOVE the "FOR AUTHORIZED INTERNAL & EXTERNAL USE ONLY" line from the hero.
- REMOVE "VERSION DATE: JULY 29, 2026" from hero (move to sidebar footer only).
- No em-dashes (—) anywhere. Use regular hyphens (-) or periods instead.
- No version labels (V1.0, BETA) as eyebrows in the hero.
- Max 1 eyebrow per 3 sections. Not every section gets a mono label above its title.

### 2. Add Visual Depth
- Add a subtle film grain overlay (SVG noise filter) as a fixed pseudo-element on the body: `position:fixed;inset:0;pointer-events:none;z-index:60;opacity:0.03;mix-blend-mode:overlay` with an SVG feTurbulence noise texture.
- Add ambient mesh gradient in dark mode: a subtle radial gradient in the cover section using `radial-gradient(circle at 30% 20%, rgba(27,94,255,0.06), transparent 50%), radial-gradient(circle at 70% 80%, rgba(0,200,255,0.04), transparent 50%)`.
- Cards should have layered shadows: `box-shadow: 0 1px 3px rgba(0,0,0,0.12), 0 0 0 1px rgba(255,255,255,0.06)` in dark mode.
- Add subtle gradient borders on key cards: use `border: 1px solid transparent; background-image: linear-gradient(var(--bg), var(--bg)), linear-gradient(135deg, rgba(27,94,255,0.15), rgba(0,200,255,0.08)); background-origin: border-box; background-clip: padding-box, border-box;`.

### 3. Upgrade Motion (use CSS only, no JS libraries)
- Add scroll-reveal animation via IntersectionObserver: elements with class `.reveal` start `opacity:0; transform:translateY(16px)` and animate to `opacity:1; transform:none` with `transition: opacity 0.6s cubic-bezier(0.23,1,0.32,1), transform 0.6s cubic-bezier(0.23,1,0.32,1)`. When observed as intersecting, add class `.reveal-in`.
- Stagger reveal: use `transition-delay: calc(var(--i, 0) * 60ms)` on grid children.
- ALL buttons: `transition: transform 160ms cubic-bezier(0.23,1,0.32,1)` and `:active { transform: scale(0.97); }`.
- Cards hover: `transition: transform 200ms cubic-bezier(0.23,1,0.32,1), box-shadow 200ms ease-out` and `:hover { transform: translateY(-2px); box-shadow: elevated; }`.
- Custom easing everywhere: `--ease-out: cubic-bezier(0.23,1,0.32,1)` and `--ease-in-out: cubic-bezier(0.77,0,0.175,1)`.
- Respect `prefers-reduced-motion: reduce` — disable all transforms, keep opacity only.

### 4. Layout Variation (at least 4 different layout families)
- NOT every section should be "tag + title + rule + grid." Vary:
  - Some sections: large quote-led (brand-purpose)
  - Some: asymmetric split (logo-dive)  
  - Some: bento grid (tokens, atoms)
  - Some: full-bleed wide section (color-system, data-table)
  - Some: stacked card layers (elevation)
  - Some: two-column with sticky left (theming, principles)
- Alternate section backgrounds: `var(--bg)` and `var(--alt)` but keep ONE theme. No mid-page theme flip.

### 5. Hero/Cover Redesign
- Full viewport height (`min-height: 100dvh`).
- Remove the scroll cue entirely.
- Add ambient mesh gradient background (see rule 2).
- Keep the 64px grid background but make it more subtle (0.015 opacity).
- Keep 4 corner brackets but make them 24px and add a subtle electric glow.
- Logo 108px white, centered with a subtle fade-in-up animation on load.
- "Opexminds" wordmark: `clamp(56px, 8vw, 96px)` Cabinet Grotesk 700, letter-spacing -0.04em.
- Add entrance animation: logo fades in first (200ms delay), then wordmark (400ms), then divider+label (600ms), then version line (800ms). Use CSS `@keyframes` with `animation-delay`.
- NO "SCROLL TO EXPLORE" text anywhere.

### 6. Enrich Thin Sections
These sections need MORE content:
- **Motion**: Add live animated easing curve demos (CSS animations), duration rationale text, and a "when to use" table for each duration.
- **Elevation**: Add interactive hover on each level card showing the shadow expanding. Add a "why elevation matters" paragraph.
- **Code**: Add copy-to-clipboard buttons on each code block. Add a 5th code snippet showing a full component example.
- **Patterns**: Add a 5th pattern (success state). Deeper descriptions for each pattern.
- **Theming**: Add a live before/after split showing the same component in dark vs light side by side.

### 7. NEW Sections to Add (3 new sections, total 24)

#### Section 22: Installation & Getting Started
- Position: after responsive, before footer.
- Content:
  - npm install snippet with copy button: `npm install @opexminds/tokens`
  - CSS import snippet: `@import "@opexminds/tokens/css";`
  - Tailwind config snippet showing how to extend the theme
  - JS/TS token import: `import { tokens } from "@opexminds/tokens";`
  - A "Quick Start" 3-step guide: 1. Install, 2. Import tokens, 3. Use components
- Layout: bento grid with code blocks and step cards.
- Has copy-to-clipboard functionality (JS).

#### Section 23: Changelog
- Content: 4-5 version entries:
  - v1.2.0 (Aug 4, 2026): Added Installation section, scroll-reveal animations, film grain overlay, layout variation across sections, 3 new sections (Installation, Changelog, Resources).
  - v1.1.0 (Aug 3, 2026): Master build with 21 sections, working interactions (toggles, toasts, combobox, streaming text, flow steps), data table with sparklines, AI-native primitives.
  - v1.0.0 (Jul 29, 2026): Initial brand & design system. Logo system, color palette, typography scale, global tokens, atoms, components, theming, patterns.
  - v0.9.0 (Jul 28, 2026): Beta release. Tokens extracted from Figma, logo SVG extracted, dark/light theme architecture defined.
- Layout: timeline with version cards, date, and bullet changes. Vertical timeline with electric blue dot markers.

#### Section 24: Resources & Downloads
- Content:
  - Logo Pack (SVG, PNG, PDF) - download card
  - Token JSON file - download card  
  - Figma File link (github.com/dhrumilmankodiya/Opex-Design_system) - external link card
  - Component Library (npm) - code snippet card
  - Brand Guidelines PDF - card
  - Icon Set (29 SVG icons) - download card
- Layout: 3x2 bento grid with icon + title + description + action button on each card.
- Each card has a download/link icon and hover state.

## EXACT TOKENS (from Figma source — DO NOT CHANGE)

### Dark Theme (default)
```css
--black:#080808; --white:#FCFCFC; --dark:#1C1C1E; --steel:#3A3A3C;
--midnight:#0A1628; --vivid:#1B5EFF; --electric:#00C8FF;
--alt:#0D0D0D; --bg:var(--black); --surface:var(--dark);
--success:#34C759; --warning:#FF9500; --error:#FF3B30;
/* Alpha series */
--t80:rgba(252,252,252,.8); --t65:rgba(252,252,252,.65); --t55:rgba(252,252,252,.55);
--t40:rgba(252,252,252,.4); --t30:rgba(252,252,252,.3); --t18:rgba(252,252,252,.18);
--t08:rgba(252,252,252,.08); --t06:rgba(252,252,252,.06); --t04:rgba(252,252,252,.04);
```

### Light Theme
```css
html[data-theme="light"]{
  --bg:#F5F7FA; --surface:#fff; --alt:#EAECEF; --text:#0F172A;
  --midnight:#EEF2FF; --electric:#0055CC; --steel:#CBD5E1;
  --t80:rgba(15,23,42,.85); --t65:rgba(15,23,42,.7); --t55:rgba(15,23,42,.65);
  --t40:rgba(15,23,42,.5); --t30:rgba(15,23,42,.38); --t18:rgba(15,23,42,.18);
  --t08:rgba(0,0,0,.07); --t06:rgba(0,0,0,.05); --t04:rgba(0,0,0,.03);
}
```

### Fonts
- Display: `'Cabinet Grotesk', sans-serif` via Fontshare: `https://api.fontshare.com/v2/css?f[]=cabinet-grotesk@700,500,400&display=swap`
- Body: `'Inter', sans-serif` via Google Fonts
- Mono: `'JetBrains Mono', monospace` via Google Fonts

### Logo
Inline SVG `<symbol id="ox" viewBox="0 0 122.748 104.092">` with this exact path:
```
M36.2105 0.107336C39.1482 -0.0666115 40.9673 -0.221277 43.657 1.28483C52.9355 6.57392 62.7007 11.8034 71.6346 17.6386C76.9231 21.0929 74.9681 25.7565 70.8385 28.8908C67.1 31.728 63.6004 35.7381 59.5343 38.0828C59.5081 37.1348 59.4553 34.3346 58.9595 33.8232C56.6061 31.3947 40.7114 22.5166 38.3065 21.8118C36.0507 22.0044 21.5038 30.8391 19.0072 32.914C17.5333 34.1387 18.1493 42.2768 18.2456 44.8952C19.9978 46.4786 23.8916 48.5601 26.0265 49.8562C30.703 52.696 35.4436 55.3704 39.9939 58.4293C42.4862 57.2937 46.9247 53.3207 49.3099 51.5878C55.9746 46.89 61.6529 42.0656 68.2367 37.15C72.6931 33.8232 79.4026 27.2761 84.6744 25.5214C87.8053 24.4793 93.4975 28.3859 96.3521 30.0968L107.143 36.5393C111.261 38.9919 115.672 41.1394 119.542 43.9372C122.798 46.3158 122.746 51.9098 122.722 55.6176C122.645 63.4047 122.915 71.302 122.556 79.0724C122.405 82.3412 120.881 84.554 118.236 86.2835C113.233 89.3989 108.019 92.5658 102.832 95.367C97.9822 97.9854 91.6713 103.205 86.382 104.071C79.395 104.306 78.4793 102.529 72.7553 99.2799C67.7354 96.4545 62.755 93.5598 57.8152 90.5965C51.2274 86.6772 42.3893 83.1158 51.7374 75.2567C54.9699 72.5387 59.6677 67.4064 63.2489 65.6186C63.4741 67.077 63.75 70.0409 64.5266 70.8168C66.5405 72.8284 82.5311 82.2001 84.3594 82.3047C87.0906 82.4607 102.841 72.5776 104.861 70.9447C105.016 67.5617 105.083 62.5489 104.853 59.2029C102.786 57.1141 84.5232 46.7387 81.4028 45.0433C78.7989 46.6441 73.3274 51.1218 70.7207 53.1612L52.5426 67.4314C48.7813 70.4446 43.0788 75.9144 38.6771 77.7829C37.5666 78.0637 34.8869 78.1648 33.9037 77.6762C24.726 73.1163 16.0008 67.407 7.02644 62.4291C4.54199 60.9618 0.854415 58.7001 0.531851 55.4455C-0.416157 45.8855 0.210338 35.6194 0.123201 25.975C0.0909188 22.4152 2.07932 19.6938 4.91075 17.8335C9.88228 14.5671 15.2895 11.7225 20.4064 8.66436C24.9092 6.18825 31.3972 1.24816 36.2105 0.107336Z
```
Reference via `<svg><use href="#ox"/></svg>`. NEVER external files.

### Icon Set (29 icons, 24x24 viewBox, 1.5px stroke, fill none)
search, settings, chevronRight, chevronDown, close, user, menu, plus, minus, check, info, warning, bell, grid, list, filter, download, upload, share, link, edit, trash, home, chart, copy, code, layers, terminal, cpu

Use the EXACT same SVG path data from the existing index.html for these icons.

### Palette Data (7 colors)
```
Core Black #080808 / RGB 8,8,8 / CMYK 0,0,0,97 - Page backgrounds, deepest surfaces
Pure White #FCFCFC / RGB 252,252,252 / CMYK 0,0,0,1 - Primary text, icons on dark
Dark Grey #1C1C1E / RGB 28,28,30 / CMYK 7,7,0,88 - Card surfaces, elevated panels
Steel Grey #3A3A3C / RGB 58,58,60 / CMYK 3,3,0,76 - Borders, dividers, disabled
Midnight Blue #0A1628 / RGB 10,22,40 / CMYK 75,45,0,84 - Deep brand surfaces
Vivid Blue #1B5EFF / RGB 27,94,255 / CMYK 89,63,0,0 - Primary CTAs, links
Electric Blue #00C8FF / RGB 0,200,255 / CMYK 100,22,0,0 - Accent highlights, data viz
```

### Type Hierarchy (10 levels)
```
Display XL: 96px / Bold 700 / Cabinet Grotesk / -0.04em / "Opexminds"
Display: 72px / Bold 700 / Cabinet Grotesk / -0.03em / "AI-Native Studio"
H1: 48px / Bold 700 / Cabinet Grotesk / -0.02em / "Build Intelligence"
H2: 32px / Bold 700 / Cabinet Grotesk / -0.01em / "Platform Overview"
H3: 24px / Medium 500 / Cabinet Grotesk / 0 / "System Components"
Body Large: 18px / Regular 400 / Inter / 0 / "Intelligent systems built for operational scale and maximum impact."
Body: 16px / Regular 400 / Inter / 0 / "Precise, authoritative engineering delivered at velocity."
Small: 14px / Regular 400 / Inter / 0 / "Configure deployment parameters for production environments."
Label: 12px / Medium 500 / JetBrains Mono / 0.12em / "SYSTEM STATUS - ACTIVE"
Caption: 11px / Regular 400 / JetBrains Mono / 0.08em / "v2.4.1 - Last updated 29 Jul 2026"
```

### Brand Content
- Purpose quote: "Opexminds: Building intelligent systems, operating platforms with infinite potential, and real impact."
- Brand Narrative: "Opexminds exists at the frontier where artificial intelligence meets operational excellence. We are not merely a software studio - we are architects of intelligent infrastructure, builders of systems that learn, adapt, and scale beyond the boundaries of conventional engineering."
- Brand Values: "Every product we deploy carries the Opexminds ethos: precision without compromise, intelligence without complexity, and impact without noise. We build for engineers who demand more - more reliability, more intelligence, more velocity - while maintaining the rigorous standards that define the best in class."
- Mission: "Make operational intelligence a dependable, compounding advantage."
- Mission desc: "We turn complex data, infrastructure and decisions into systems that create clarity today and learn their way to better outcomes tomorrow."
- Pillars: Intelligence (AI-native, every system learns), Precision (measure everything), Velocity (deploy in minutes), Impact (engineer measurable results)
- Adjectives: Precise, Authoritative, Forward-Thinking, Intelligent, Technical, Minimal, Confident, Systematic, Uncompromising, Scalable
- WE ARE: Technically precise and direct, Confident without arrogance, Informative and dense with signal, Future-oriented with present proof
- WE ARE NOT: Buzzword-heavy or vague, Casual or informal in core copy, Explaining obvious concepts, Hyperbolic ("revolutionary", "best-ever")
- Principles: Token-First Architecture, Compositional Hierarchy, Dark-Native Design, Accessibility by Default, Code Parity

### Spacing Scale (4px base)
--space-1: 4px, --space-2: 8px, --space-3: 12px, --space-4: 16px, --space-6: 24px, --space-8: 32px, --space-12: 48px, --space-16: 64px, --space-24: 96px, --space-32: 128px

### Layout Grids
Desktop: 12 cols, 24px gutter, 80px margin, 1440px max
Tablet: 8 cols, 16px gutter, 32px margin, 1024px max
Mobile: 4 cols, 12px gutter, 16px margin, 390px max

### Corner Radius
0px (None), 2px (Subtle), 4px (Default), 8px (Medium), 12px (Large), 999px (Pill)

### Border Specs
Default: 1px white 8%, Subtle: 1px white 14%, Hover: Vivid Blue 50%, Focus: 2px Vivid Blue, Error: 1px #FF3B30, Success: 1px #34C759

### Motion Durations
Micro: 100ms (hover states), Standard: 200ms (dropdowns, tooltips), Complex: 350ms (modals, drawers), Spatial: 500ms (route transitions)

### Elevation Levels
L0 Canvas: no shadow, L1 Cards: 4px/20px shadow, L2 Floating: 12px/32px shadow, L3 Modals: 24px/64px shadow

### Data Table Data
```
API Gateway v3.2 / production / 99.97% / 42ms / [91,95,94,98,99,99,100] / live
ML Pipeline Core / production / 87.30% / 183ms / [72,78,80,83,85,88,87] / watch
Vector Store DB / production / 71.20% / 296ms / [95,90,84,79,74,73,71] / watch
Auth Service v2 / production / 99.99% / 38ms / [99,100,100,99,100,100,100] / live
Log Aggregator / staging / 0.00% / - / [88,76,52,30,10,0,0] / watch
```

### Flow Steps (Patterns)
1. Configure - Define deployment parameters, environment variables, resource allocation, and target cluster.
2. Review - Inspect the diff, validate configuration, check for breaking changes and dependency conflicts.
3. Deploy - Initiate the deployment pipeline. Automated health checks run in parallel with traffic shifting.
4. Monitor - Track real-time metrics: latency p99, error rates, throughput, and distributed system health.

### Theme Map (Dark to Light)
Canvas: #080808 -> #F5F7FA
Text primary: #FCFCFC -> #0F172A
Surface: #1C1C1E -> #FFFFFF
Structure: #3A3A3C -> #CBD5E1
Brand depth: #0A1628 -> #EEF2FF
Primary accent: #1B5EFF -> #1B5EFF (same)
Electric accent: #00C8FF -> #0055CC

## Technical Requirements
- SINGLE self-contained index.html file. All CSS inline in `<style>`. All JS inline in `<script>`.
- `data-theme="dark|light"` on `<html>`. CSS variable swap.
- Fixed left sidebar 216px desktop (logo+wordmark top, grouped nav, theme toggle). Mobile: 52px top bar + hamburger drawer.
- IntersectionObserver for active-section tracking in sidebar nav.
- IntersectionObserver for scroll-reveal animations (class `.reveal` -> `.reveal-in`).
- All interactions work with vanilla JS (no libraries).
- prefers-reduced-motion support.
- Responsive: desktop/tablet/mobile layouts.
- 24 sections total (original 21 + Installation + Changelog + Resources).
- Font links: Fontshare for Cabinet Grotesk, Google Fonts for Inter + JetBrains Mono.
- Section nav groups: "Brand Guidelines" (1-6), "Design System" (7-13), "Engineering Specs" (14-19), "Implementation" (20-24).
- Sidebar footer: "© 2026 OPEXMINDS" and "AUG 04, 2026".
- Footer text: "OPEXMINDS - INTEGRATED BRAND & DESIGN SYSTEM © 2026" (no version number, no em-dash).
- Title: `<title>Opexminds - Integrated Brand & Design System</title>` (no em-dash).

## Copy-to-clipboard for code blocks and installation snippets
Add a small "Copy" button on each code block. On click, use `navigator.clipboard.writeText()` and show "Copied!" for 2 seconds.

## Output
Write the COMPLETE file to `/home/ubuntu/opexminds-designsystem/index.html`. Expected size: 90-130KB. Do NOT compress content. This is the flagship deliverable. Take as long as you need.
