# Opexminds Design Principles (from our design skills)

## From design-taste-frontend (anti-slop)
- Never default to: AI-purple gradients, centered hero over dark mesh, three equal feature cards, generic glassmorphism everywhere, Inter + slate-900. These are LLM defaults. Reach past them.
- One design system per project. One accent color, used identically everywhere. Shape consistency: one corner-radius system.
- Hero: headline max 2 lines, subtext max 20 words, CTA visible without scroll, top padding max 6rem.
- ZERO em-dashes. Use hyphen or restructure.
- No decorative section-number eyebrows on every section - max 1 per 3 sections. Use plain language labels.
- Cards only when elevation communicates hierarchy. Otherwise use borders/negative space.
- No fake screenshots built from divs. Use real rendered content.
- Buttons: text readable against background (WCAG AA 4.5:1), no wrapped CTA labels.
- Motion must be motivated: hierarchy, storytelling, feedback, state transition. Not "looks cool".
- Respect prefers-reduced-motion.
- Real images over placeholders.

## From emil-design-eng (polish)
- Buttons: transform scale(0.97) on :active. Transition transform 160ms ease-out.
- Never animate from scale(0). Start scale(0.95) + opacity 0.
- Custom easing: --ease-out: cubic-bezier(0.23,1,0.32,1); strong ease-in-out: cubic-bezier(0.77,0,0.175,1).
- UI animations under 300ms. 100-160ms button press. 125-200ms tooltips. 150-250ms dropdowns. 200-500ms modals.
- Use CSS transitions over keyframes for interruptible UI.
- Only animate transform and opacity (GPU).
- Popovers scale from trigger, not center.
- Spring animations for alive-feel: stiffness 100, damping 10, subtle bounce 0.1-0.3.
- Blur (max 20px) masks imperfect transitions.
- Stagger entries 30-80ms between items.
- Focus states must be visible.

## From ui-ux-pro-max
- Standard breakpoints: sm 640, md 768, lg 1024, xl 1280, 2xl 1536.
- Touch targets min 44x44px.
- min-h-[100dvh] never h-screen.
- Grid over flex-math.
- Loading/empty/error states for all interactive components.

## From ckm:brand / brand-guidelines (from loaded brand skills)
- Brand consistency: logo clear space, correct color usage, approved typography.
- Dark-first design: near-black backgrounds, high contrast, premium.
- Monochrome-first logo usage: white on dark, dark on light, accent variants approved.
- Every color has a semantic role. Consistent usage rules documented.

## The Opexminds Figma brand (from figma-src, THE SOURCE OF TRUTH)
- Fonts: Cabinet Grotesk (display, via Fontshare), Inter (body), JetBrains Mono (labels/data)
- Colors: Core Black #080808, Pure White #FCFCFC, Dark Grey #1C1C1E, Steel Grey #3A3A3C, Midnight Blue #0A1628, Vivid Blue #1B5EFF, Electric Blue #00C8FF
- Logo: inline SVG path viewBox "0 0 122.748 104.092" (the LOGO_SVG constant)
- Sections structure, sidebar nav 216px, section padding 80px 64px, hairline grids via gap:1px + background t06
