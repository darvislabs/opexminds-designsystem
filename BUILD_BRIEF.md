# Opexminds Brand Design System - Build Brief

You are building a world-class brand design system for **Opexminds** - an AI-powered operational intelligence and cost optimization platform (think Vercel/Linear/Stripe level of polish).

## Working Directory
/home/ubuntu/opexminds-designsystem/

## Official Asset
`opexminds-logo-reference.jpg` - the ONLY approved logo asset. A vertical lockup with a modular geometric symbol above a wordmark on a dark background. Use this file for all logo displays. DO NOT generate or substitute any other logos.

## Deliverable
One single self-contained `index.html` file (zero external dependencies except Google Fonts). Dark mode only. Must be stunning, modern, 2026-level design.

## Design Direction
- **Dark theme**: near-black layered surfaces (#050609 base, #0A0B0F surface, #0F1117 elevated)
- **Fonts**: Space Grotesk (display/UI) + JetBrains Mono (labels/code) via Google Fonts
- **Accent**: Blue gradient #5B8DEF to #7AB8E8 (matches logo's blue tones). Single accent used consistently.
- **Text**: #EDEEF0 primary, #8A8D94 secondary, #4A4D54 tertiary
- **Borders**: rgba(255,255,255,0.06), hover rgba(255,255,255,0.1)
- **Radius**: 14px cards, 24px large containers
- **Motion**: subtle hover lifts (-3px translateY), smooth transitions with cubic-bezier(0.22,1,0.36,1), glassmorphism nav with backdrop blur
- **Texture**: subtle noise overlay via inline SVG data URI (opacity 0.015)
- **No em-dashes anywhere** (use hyphens or restructure)
- **No emoji icons** - build icons with CSS/SVG geometric shapes
- Monospace labels for section numbers and metadata
- Generous whitespace, 120px section padding
- Terminal/code aesthetic touches (mono metadata in corners, bracketed labels like `// SECTION`)

## 19 Sections (all required)
1. **01 / Identity** - Brand philosophy, 8 principle cards (grid 4-col): Intelligence First, Precision Over Ornament, Infinite Scalability, Timeless Modernity, Modular Architecture, Monochromatic First, Iconic Simplicity, Operational Focus
2. **02 / Logo System** - Show the real logo (opexminds-logo-reference.jpg) on dark AND light backgrounds, technical specs table (configuration, background, min sizes, clear space, file formats), size spectrum visual (16px to 96px), 6 do/don't usage cards
3. **03 / Color System** - Primary swatch grid (Void #050609, Surface #0A0B0F, Surface 2 #0F1117, Accent #5B8DEF, Accent 2 #7AB8E8, Text #EDEEF0), semantic colors (Positive #3DD68C, Warning #F5A623, Negative #E84545), 3 gradient cards (Primary, Deep Brand, Optimization), WCAG contrast table
4. **04 / Typography** - Big "Aa" specimen with gradient text, type scale rows: Display 72px, H1 48px, H2 32px, H3 24px, Body 16px, Small 13px, Mono 14px, Mono label 11px. Each with mono label showing font/size/weight
5. **05 / Grid** - 12-column visual demo, key metrics (12 columns, 8px gutter, 1200px max, 8px base), spacing scale bars (4px to 96px)
6. **06 / Iconography** - 12 CSS/SVG geometric icons in grid (dashboard, cost, analyze, optimize, ai, trends, alerts, team, settings, reports, integrate, security), each with tinted container + glyph, construction rules panel below
7. **07 / Motion** - 4 animated demo cards with LIVE CSS animations: Fade (200ms ease-out), Slide (300ms), Scale (250ms), Spring (400ms cubic-bezier(0.34,1.56,0.64,1)). Timing system table
8. **08 / Voice & Tone** - 3 cards: Precise, Confident, Actionable - each with example italic quote
9. **09 / Accessibility** - 6 WCAG compliance cards with badges (Color Contrast AA/AAA, Focus States 2.4.7, Reduced Motion 2.3.3, Screen Readers 4.1.2, Touch Targets 2.5.8, Text Resize 1.4.4)
10. **10 / Applications** - 3 mockup contexts using the real logo: mobile app icon on dark, app header horizontal lockup, favicon
11. **11-19 / Extended** - 9 compact cards in 2-col grid: Data Visualization, Illustration System, UI Components, Marketing Patterns, Email Templates, Photography Direction, Co-Branding, Merchandise, Physical Environment. Each with number + title + one-line description

## Structure
- Fixed glassmorphism nav (56px, backdrop blur, logo dot + wordmark left, section links right, hides on mobile)
- Full-viewport hero: mono metadata corner (// OPEXMINDS / // BRAND SYSTEM v2.0 / // STATUS: LIVE), gradient headline "Opexminds", subtitle, the real logo in a framed card below
- Each section: mono section number (01 / IDENTITY) + large title + description, then content
- Footer with mark, name, tagline, mono copyright

## Build Rules
- Write the COMPLETE file to /home/ubuntu/opexminds-designsystem/index.html
- All image references must use relative path opexminds-logo-reference.jpg
- Valid HTML5, semantic tags, proper meta viewport
- Responsive: grid collapses to 1-col under 768px, nav links hide
- The file should be visually stunning - this is the centerpiece deliverable
