# OPEXMINDS DESIGN SYSTEM — MASTER BUILD (Figma+ Quality)

## Your Mission
Build the definitive Opexminds brand & design system as a SINGLE self-contained `index.html`. This must be BETTER than the Figma reference in figma-src/. Richer content, more polish, more working interactions, deeper sections. This is the flagship deliverable.

## MANDATORY: Read these FIRST
1. `DESIGN_PRINCIPLES.md` (in this dir) — design quality rules from our skills. Follow them.
2. `figma-src/src/ThemeContext.tsx` — exact tokens (dark + light).
3. `figma-src/src/App.tsx` — full content of core sections + LOGO_SVG path + ICON_PATHS (29 icons).
4. `figma-src/src/sections/V2.tsx` — V2 engineering sections content.
5. `figma-src/src/index.css` — font imports.

## Non-Negotiable Technical Requirements
- Cabinet Grotesk via Fontshare: https://api.fontshare.com/v2/css?f[]=cabinet-grotesk@700,500,400&display=swap
- Inter + JetBrains Mono via Google Fonts
- Logo: inline SVG `<symbol id="ox">` with the exact LOGO_SVG path from App.tsx (viewBox 0 0 122.748 104.092), referenced via `<svg><use href="#ox"/></svg>`. NEVER external files.
- Theme: `data-theme="dark"|"light"` on <html>, CSS variables swap. Dark: #080808 bg. Light: #F5F7FA bg.
- Fixed left sidebar 216px desktop (logo+wordmark top, grouped nav, theme toggle bottom), mobile: 52px top bar + hamburger drawer.
- All 21 sections present: cover, brand-purpose, logo-dive, color-system, typography, imagery, design-overview, global-tokens, atoms, components, theming, patterns, code, motion, elevation, advanced, data-table, ai-native, accessibility, adaptive-theme, responsive.
- IntersectionObserver active-section tracking in sidebar. Smooth scroll.
- prefers-reduced-motion support.
- Responsive: desktop/tablet/mobile layouts.

## Content Depth Requirement (THE KEY DIFFERENCE - this is where you beat the Figma version)
The previous build was too thin. EVERY section must have FULL, RICH content. Do not abbreviate. Write complete copy, complete data, complete component states. Use the Figma source for all real copy (brand narrative, values, pillars, palette data with HEX/RGB/CMYK, type hierarchy, system principles, voice guidelines, adjectives, etc.) and then EXPAND beyond it with additional valuable content.

### Section-by-section depth requirements:

**1. cover** — Full-viewport hero: 64px grid background (rgba(27,94,255,0.025)), 4 corner brackets (electric), centered logo 108 white, "Opexminds" clamp(56px,8vw,96px) Cabinet 700 -0.04em, divider lines + "Brand & Design System" mono electric, version mono lines. PLUS a scroll cue and subtle entrance animations (fade-up stagger).

**2. brand-purpose** — SectionTag 01 Brand Foundation, title 1.1 Brand Purpose. Purpose quote (border-left 3px vivid, Cabinet 22-34px italic feel). Brand Narrative + Brand Values 2-col (FULL copy from App.tsx). 4 pillars grid (Intelligence/Precision/Velocity/Impact) with FULL descriptions from App.tsx, each cell borderTop 2px vivid, mono number, Cabinet title, Inter desc. ADD: a mission statement block and 3 "what we do" capability chips.

**3. logo-dive** — SectionTag 02 Identity System, 1.2 Logo Deep Dive. Full lockups: Primary Horizontal (logo 32 + wordmark 26 Cabinet), Vertical (stacked), Symbol Only (52), Wordmark Only (26 on vivid bg) — all 4 in hairline grid. Grid & Construction: 8px grid overlay + centered logo 88 + electric center dot + construction note (122.748x104.092, 1.18:1 ratio). Clearance Zones: X safe area with dashed vivid border + X markers + spec grid (min clearance 0.5x, preferred 1x, X=104 units, min digital 24px). Do's & Don'ts: 6 cells (White on dark ✓, Electric accent ✓, Black on white ✓, Never rotate ✗ rotated, Never distort ✗ scaled, No unapproved colors ✗ red bg). ADD: a "logo anatomy" callout with labeled parts and a "minimum sizes" strip (16/24/32/48/64/96px).

**4. color-system** — SectionTag 03 Color Architecture, 1.3 Color System. ALL 7 palette swatches (Core Black, Pure White, Dark Grey, Steel Grey, Midnight Blue, Vivid Blue, Electric Blue) each with: 110px color block, 4 tint strips (20/40/60/80%), name, HEX/RGB/CMYK mono rows, usage note. Primary (4-col) + Secondary (3-col) groups. Color Usage Rules table: Backgrounds / Typography / CTAs / Accents / Structure rows with color chips + notes (FULL text from App.tsx). ADD: a semantic/status color row (success #34C759, warning #FF9500, error #FF3B30, info electric) with usage rules, and a gradient showcase (vivid→electric, midnight→vivid).

**5. typography** — SectionTag 04 Type System, 1.4 Typography. 3 typeface cards (Cabinet Grotesk / Inter / JetBrains Mono) each with "ABCDEF abcdef" specimen 30px, role, name, note. Full character specimen (uppercase 28px 700, lowercase 28px, punctuation 18px, pangram 16px, brand line 14px). Type Hierarchy Scale: 10 rows (Display XL 96px, Display 72px, H1 48px, H2 32px, H3 24px, Body Large 18px, Body 16px, Small 14px, Label 12px mono electric, Caption 11px) each with name/size/weight/face mono columns + LIVE sample. ADD: an interactive size slider or at least hover states on rows.

**6. imagery** — SectionTag 05 Imagery & Voice, 1.5 Imagery & Tone of Voice. Mood board: 2fr 1fr 1fr grid 2 rows 220px with the Unsplash URLs from App.tsx (opacity .75, saturate .55). Approved/Not approved note. Brand Adjectives: 10 outlined chips (FULL list from App.tsx with colors). Voice Guidelines: WE ARE (green #34C759 arrows) / WE ARE NOT (red #FF3B30 X) FULL items.

**7. design-overview** — SectionTag 06 System Architecture, 2.0 Design System Overview. Atomic Design layer model: 6 stacked bars (Pages 100% vivid → Design Tokens 40% dark) with desc + Foundation baseline. System Principles: 5 FULL rows from App.tsx (Token-First, Compositional Hierarchy, Dark-Native, Accessibility by Default, Code Parity).

**8. global-tokens** — SectionTag 07 Global Tokens, 2.1 Global Tokens. 4px spacing scale: 10 rows (--space-1 4px through --space-32 128px) with vivid bars. Layout grids: Desktop 12/24/80/1440, Tablet 8/16/32/1024, Mobile 4/12/16/390 with column viz. Corner radius: 6 squares (0/2/4/8/12/999). Border & stroke specs: 6 rows (Default 1px 8%, Subtle 14%, Hover vivid 50%, Focus 2px vivid, Error #FF3B30, Success #34C759). ADD: shadow/elevation token strip.

**9. atoms** — SectionTag 08 Core Atoms, 2.2 Key Elements & Atoms. Buttons: PRIMARY states (Default vivid / Hover #0047E6 / Active #0039CC scale .98 / Disabled / Loading spinner) + SECONDARY (Ghost, Tinted, Destructive #FF3B30). Inputs: default/focus (2px vivid)/error (#FF3B30 border) states. Icon set: ALL 29 icons from ICON_PATHS rendered as inline SVGs (search settings chevronRight chevronDown close user menu plus minus check info warning bell grid list filter download upload share link edit trash home chart copy code layers terminal cpu) in a grid with mono labels. Tags: 6 variants.

**10. components** — SectionTag 09 Component Library, 2.3 Components. Cards (data card, deploy card), alerts (success green, warning amber, error red), modal preview, navigation pattern, progress indicators. Rendered live, not mocked.

**11. theming** — SectionTag 10 Theme System, 2.4 Theming. Token mapping table (dark→light for every token), theme architecture note, live theme toggle demo button.

**12. patterns** — SectionTag 11 UX Patterns, 2.5 Design Patterns. Deploy flow (Configure → Review → Deploy → Monitor), empty state, loading skeleton, error recovery pattern.

**13. code** — SectionTag 12 Code Reference, 2.6 Code Snippets. Code blocks (dark bg, JetBrains Mono, syntax-ish coloring) showing: CSS variable usage, theme tokens, component example, logo SVG usage.

**14. motion** — V2 Motion Design. Duration tokens (100ms micro, 200ms standard, 350ms complex, 500ms spatial). Easing demo cards with LIVE animated curves/boxes (standard, decelerate, emphasized, spring). Hover-triggered animations.

**15. elevation** — V2 Depth & Elevation. 4 levels (L0 canvas, L1 cards, L2 floating menus, L3 modals) rendered as stacked cards with shadows.

**16. advanced** — V2 Advanced Components. WORKING: toggle switches (click toggles), combobox (click opens, click option selects), file dropzone (click adds file name), toast system (button click shows toast, auto-dismisses), tooltip (hover shows).

**17. data-table** — V2 Enterprise Data Table. REAL table: header row (Service, Environment, Uptime, Latency, Trend), 4+ data rows from App.tsx, sparkline SVG in trend column, status pills (LIVE green, WATCH amber), hover row highlight, sortable feel.

**18. ai-native** — V2 AI-Native Primitives. Streaming text effect (typewriter with cursor), feedback buttons (thumbs up/down with click states), AI insight cards, chat input mock.

**19. accessibility** — V2 Accessibility. WCAG 2.1 AA cards (contrast, focus, reduced motion, screen readers, touch targets, text resize), keyboard nav note, focus ring demo.

**20. adaptive-theme** — Implementation. One token architecture, two environments. Live token preview with toggle button. Before/after color mapping.

**21. responsive** — Responsive System. Breakpoint cards (Desktop 1080+, Tablet 768-1080, Mobile <768) with column specs. Responsive behavior notes. Footer: OPEXMINDS — INTEGRATED BRAND & DESIGN SYSTEM V1.0 © 2026.

## Design Quality Bar (exceed Figma)
- Hairline-separated grids (gap:1px, bg t06) — the signature look.
- Every section header: mono tag with electric number + line + label, then big Cabinet title, then HR.
- Hover states everywhere: cards lift 1-2px or border brightens, buttons respond, nav active highlight.
- Real rendered content everywhere - no placeholder text, no lorem ipsum.
- Full color depth: use the t-series alpha tokens for depth layering.
- Interactive elements must WORK (JS at end of body, clean vanilla JS).
- The sidebar must feel premium: grouped sections, active indicator on left edge (electric), hover states.
- Mobile drawer: slides in with transition, overlay backdrop.

## Output
Write the COMPLETE file to `index.html`. Expected size: 60KB-150KB (rich content). Do NOT compress content to save size. This is the flagship. Take as long as you need.
