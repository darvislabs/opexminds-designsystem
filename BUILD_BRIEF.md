# Opexminds Design System - Rebuild to Figma Standard

## Context
There is a Figma-designed React app at `figma-src/` (in this same directory). It is the DESIGN REFERENCE - the gold standard. Your job: rebuild the single-file `index.html` in THIS directory (overwrite it) so it matches the Figma design's quality, structure, tokens, and components - but as ONE self-contained HTML file (no React, no build step).

## READ THESE REFERENCE FILES FIRST (in order)
1. `figma-src/src/ThemeContext.tsx` - ALL design tokens (colors, alpha scale, light/dark themes). Copy these EXACT values.
2. `figma-src/src/App.tsx` - the main design system content: Cover, Brand Purpose, Logo Deep Dive, Color System, Typography, Imagery, Design Overview, Global Tokens, Atoms, Components, Theming, Patterns, Code sections. Also contains the LOGO_SVG path (the actual vector logo!) and all icon SVG paths.
3. `figma-src/src/sections/V2.tsx` - V2 engineering sections: Motion, Elevation, Advanced Components, Data Table, AI-Native, Accessibility.
4. `figma-src/index.html` + `figma-src/src/index.css` - font imports.

## Design Tokens (copy EXACTLY from ThemeContext.tsx)
Dark theme:
- black: #080808 (page bg)
- white: #FCFCFC (primary text)
- dark: #1C1C1E (card surfaces)
- steel: #3A3A3C (borders/dividers)
- midnight: #0A1628 (deep brand surfaces, alt section bg)
- vivid: #1B5EFF (primary accent - CTAs, links)
- electric: #00C8FF (secondary accent - labels, charts, highlights)
- altBg: #0D0D0D (alternate section background)
- logoFill: #FCFCFC
- Alpha scale: t80..t025 = rgba(252,252,252,X) from 0.8 down to 0.025

Light theme (also include, with theme toggle):
- black: #F5F7FA, white: #0F172A, dark: #FFFFFF, steel: #CBD5E1, midnight: #EEF2FF, vivid: #1B5EFF, electric: #0055CC, altBg: #EAECEF, logoFill: #0F172A
- Alpha scale: rgba(15,23,42,X) roughly

## Fonts (from index.css)
```html
<link href="https://api.fontshare.com/v2/css?f[]=cabinet-grotesk@700,500,400&display=swap" rel="stylesheet">
<link href="https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700&display=swap" rel="stylesheet">
<link href="https://fonts.googleapis.com/css2?family=JetBrains+Mono:wght@400;500;600&display=swap" rel="stylesheet">
```
- Display/headlines: Cabinet Grotesk (bold geometric)
- Body/UI: Inter
- Labels/code/data: JetBrains Mono

## LOGO (CRITICAL)
Use the LOGO_SVG path constant from App.tsx (the `OpexLogo` component, viewBox "0 0 122.748 104.092"). Render it as an inline SVG element - this is the actual official Opexminds symbol. Use it:
- In the cover hero (size ~108)
- In sidebar header (size ~14-16 next to "Opexminds" wordmark)
- In Logo section lockups
- Color via fill (logoFill / white / vivid / electric variants)

Wordmark text: "Opexminds" in Cabinet Grotesk 700.

## Layout Structure (match Figma exactly)
- Fixed LEFT SIDEBAR (216px) on desktop: logo+wordmark header, then grouped nav links (Brand Foundation: cover/brand-purpose/logo-dive/color-system/typography/imagery; System Architecture: design-overview/global-tokens/atoms/components/theming/patterns/code; V2 Engineering Specs: motion/elevation/advanced/data-table/ai-native/accessibility; Implementation: adaptive-theme/responsive). Active section highlighted. Theme toggle at top.
- Mobile: top bar 52px with hamburger opening sidebar drawer.
- Main content: margin-left 216px (desktop), 0 (mobile) + padding-top 52 (mobile).
- Each section: `<section id="...">` with background C.black (or C.altBg/midnight for dark variants), padding 80px 64px desktop / 64px 40px tablet / 48px 20px mobile, borderBottom 1px solid t05.
- Section header pattern: SectionTag (mono 11px electric label "01" + 32px line + mono 10px uppercase label) + DisplayTitle (Cabinet Grotesk, clamp(32px,4vw,48px), 700, -0.02em) + HR (1px t07, margin 48px 0).
- MonoLabel: mono 10px, 0.13em uppercase, with a flex line extending to the right (1px t06).
- Cards/grids: grid with `gap:1px` and `background: t06` to create hairline-separated cells, each cell background black.

## Sections (build ALL of these, in this order, matching the Figma content):
1. **Cover** (id=cover): 100vh, grid overlay background (64px grid lines rgba(27,94,255,0.025)), corner brackets (20px squares with electric borders at 4 corners), centered: OpexLogo 108 white, "Opexminds" Cabinet Grotesk clamp(56px,8vw,96px) 700 -0.04em, divider lines + "Brand & Design System" mono 11px electric 0.2em, "Integrated Brand & Design System V1.0" mono, "Version Date: July 29, 2026" mono, "For Authorized Internal & External Use Only" mono dim.
2. **Brand Purpose** (id=brand-purpose): SectionTag 01 Brand Foundation, title "1.1 Brand Purpose", purpose quote (Cabinet Grotesk 22-34px, left border 3px vivid, padding-left 32px), 2 columns Brand Narrative + Brand Values (Inter 16px t65), 4 pillars grid (01 Intelligence, 02 Precision, 03 Velocity, 04 Impact - each with borderTop 2px vivid, mono num, Cabinet title, Inter desc).
3. **Logo Deep Dive** (id=logo-dive, altBg bg): SectionTag 02 Identity System, title "1.2 Logo Deep Dive". Core Logo Lockups: 4 cells (Primary Horizontal: logo 32 + wordmark 26px; Vertical: logo 32 + wordmark 20px stacked; Symbol Only: logo 52; Wordmark Only: 26px on vivid bg). Grid & Construction: 8px grid overlay with dashed lines + centered logo 88 + electric center dot, note about 122.748x104.092 ratio. Clearance Zones: X safe area (dashed vivid border, X markers), spec mini-grid (Minimum clearance 0.5x, Preferred 1x, X = symbol height 104 units, Min digital 24px). Do's & Don'ts: 6 cells (White on dark DO, Electric accent DO, Black on white DO, Never rotate DON'T rotated 40deg, Never distort DON'T scaleX(1.5) 35% opacity, No unapproved colors DON'T red bg).
4. **Color System** (id=color-system): SectionTag 03 Color Architecture, title "1.3 Color System". Primary Palette: Core Black #080808, Pure White #FCFCFC, Dark Grey #1C1C1E, Steel Grey #3A3A3C (each swatch: 110px color block, 4 tint strips 18px, name, HEX/RGB/CMYK mono rows, usage note, 20/40/60/80% labels). Secondary Palette: Midnight Blue #0A1628, Vivid Blue #1B5EFF, Electric Blue #00C8FF (3-col). Color Usage Rules table: Backgrounds/Typography/CTAs/Accents/Structure rows with role, color chips, note.
5. **Typography** (id=typography, altBg): SectionTag 04 Type System, title "1.4 Typography". 3 typeface cards (Cabinet Grotesk "ABCDEF abcdef" 30px + role/name/note; Inter; JetBrains Mono). Full character specimen (Cabinet Grotesk: uppercase 28px 700, lowercase 28px 700, punctuation 18px 400, pangram 16px, brand line 14px). Type Hierarchy Scale table (10 rows: Display XL 96px, Display 72px, H1 48px, H2 32px, H3 24px, Body Large 18px, Body 16px, Small 14px, Label 12px JetBrains Mono 0.12em electric, Caption 11px) - each row: name mono, size mono vivid, weight mono, face mono, live sample.
6. **Imagery & Tone** (id=imagery): SectionTag 05 Imagery & Voice, title "1.5 Imagery & Tone of Voice". Mood board: 2fr 1fr 1fr grid, 2 rows 220px, Unsplash images (use the exact URLs from App.tsx) with opacity 0.75 saturate(0.55). Approved/Not approved note. Brand Adjectives: 10 outlined chips (Precise vivid, Authoritative electric, Forward-Thinking vivid, Intelligent electric, Technical vivid, Minimal t28, Confident electric, Systematic t28, Uncompromising vivid, Scalable t28). Voice Guidelines: WE ARE (green #34C759, arrows, 4 items) / WE ARE NOT (red #FF3B30, X, 4 items).
7. **Design Overview** (id=design-overview, altBg): SectionTag 06 System Architecture, title "2.0 Design System Overview". Atomic Design layer model: 6 stacked bars (Pages 100% vivid, Templates 88% #1549e0, Organisms 76% midnight, Molecules 64% #0F2040, Atoms 52% steel, Design Tokens 40% dark) with label + desc, then vertical line + "Foundation". System Principles: 5 rows (01 Token-First Architecture, 02 Compositional Hierarchy, 03 Dark-Native Design, 04 Accessibility by Default, 05 Code Parity).
8. **Global Tokens** (id=global-tokens): SectionTag 07 Global Tokens, title "2.1 Global Tokens". 4px Base Spacing Scale: 10 rows (--space-1 4px ... --space-32 128px) with vivid bars (width px*1.8). Layout Grid System: 3 cards (Desktop 12 cols/24px/80px/1440px, Tablet 8/16/32/1024, Mobile 4/12/16/390) each with column visualization. Corner Radius Scale: 6 squares (None 0, Subtle 2, Default 4, Medium 8, Large 12, Pill 999). Border & Stroke Specs: 6 rows (Default 1px white8%, Subtle 14%, Hover vivid 50%, Focus 2px vivid, Error #FF3B30, Success #34C759).
9. **Atoms** (id=atoms, altBg): SectionTag 08 Core Atoms, title "2.2 Key Elements & Atoms". Button states: PRIMARY (Default vivid, Hover #0047E6, Active #0039CC scale .98, Disabled 22% opacity, Loading with spinner) + SECONDARY (Ghost, Tinted vivid 10%, Destructive #FF3B30). Then inputs (with focus/error states), icon set (all 29 icons from ICON_PATHS: search settings chevronRight chevronDown close user menu plus minus check info warning bell grid list filter download upload share link edit trash home chart copy code layers terminal cpu - render each as SVG 20px with label), tags.
10. **Components** (id=components): SectionTag 09, title "2.3 Components" - cards, modals, navigation patterns, alerts/banners (match whatever App.tsx shows).
11. **Theming** (id=theming, altBg): SectionTag 10, title "2.4 Theming" - theme architecture, token mapping, dark/light comparison.
12. **Patterns** (id=patterns): SectionTag 11, title "2.5 Patterns" - layout patterns, empty states, loading states.
13. **Code** (id=code, altBg): SectionTag 12, title "2.6 Code" - code blocks with mono styling.
14. **Motion** (id=motion): V2 section - bezier curve diagrams, easing demos (use the EasingDemo component logic: animated dots/boxes with different easings), timing tokens.
15. **Elevation** (id=elevation, altBg): V2 section - shadow/elevation scale cards.
16. **Advanced Components** (id=advanced): V2 section - toggle switch, combo box, file dropzone, toast stack (build with CSS + minimal JS for interactivity: toggles work, combobox opens, dropzone highlights).
17. **Data Table** (id=data-table, altBg): V2 section - the table from DataTableSection with sparklines (SVG polyline), status pills, sortable headers.
18. **AI-Native** (id=ai-native): V2 section - streaming text effect, feedback buttons, AI chat mock.
19. **Accessibility** (id=accessibility, altBg): V2 section - WCAG cards, focus states, contrast.
20. **Adaptive Theme** (id=adaptive-theme): theme system explainer with live demo.
21. **Responsive System** (id=responsive): breakpoint cards (Desktop 1080+, Tablet 768-1080, Mobile <768), responsive patterns.

## Interactions (must work - this is where the single-file version can beat a static mock)
- Theme toggle: dark/light switch via CSS variables + JS class toggle on body. All tokens swap.
- Sidebar: active section tracking via IntersectionObserver, click scrolls smooth.
- Mobile: hamburger opens sidebar drawer.
- V2 components: toggle switches actually toggle, combobox opens/closes, toasts appear on button click, streaming text animates, data table rows hover.
- Reduced motion: @media (prefers-reduced-motion: reduce) disables animations.

## CSS Architecture
- Use CSS custom properties on :root for dark tokens, [data-theme="light"] overrides.
- All the alpha tokens as variables: --t80 ... --t025.
- Transitions: transform/border-color/background 0.3s cubic-bezier(0.4, 0, 0.2, 1).
- Focus states: 2px solid vivid.
- Scrollbar: 4px, thumb rgba(252,252,252,0.1).
- Keyframes needed: spin (loading), pulse, blink, slideIn.

## Output
Write the COMPLETE single-file HTML to `index.html` in this directory. Everything inline (CSS in <style>, JS in <script> at end of body, icons as inline SVG). No external files except the 3 font links. Must be production-quality, visually stunning, matching the Figma reference exactly. The file will be large - that's fine. Take your time and do it properly.
