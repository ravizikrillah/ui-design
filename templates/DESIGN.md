# Design System: [Project Name]

> Declarative design specification for AI coding agents and design engines.

---

## 1. Visual Theme & Atmosphere
- **Aesthetic Direction:** [e.g. Minimalist Dark Tech / Editorial Monospaced / Refined B2B SaaS]
- **Atmosphere:** [e.g. Clinical, calm, high-contrast, mathematically spaced]
- **Core Dials:**
  - `DESIGN_VARIANCE`: 7 (Offset asymmetric grids, split hero, distinct section rhythms)
  - `MOTION_INTENSITY`: 6 (Subtle spring micro-interactions, scroll-triggered reveals)
  - `VISUAL_DENSITY`: 4 (Balanced breathing room, generous whitespace, clear typography hierarchy)

---

## 2. Color Palette & Functional Roles
- **Canvas:** `#09090b` (Deep Zinc page background)
- **Surface Layer 1:** `#18181b` (Primary card and container background)
- **Surface Layer 2:** `#27272a` (Elevated modals, tooltips, dropdowns)
- **Border Subtle:** `rgba(255, 255, 255, 0.08)` (Structural 1px dividers and cards)
- **Border Focused:** `rgba(255, 255, 255, 0.2)` (Hover and selected borders)
- **Text High-Contrast:** `#fafafa` (Headings, primary CTA labels)
- **Text Muted:** `#a1a1aa` (Body text, descriptive paragraphs, secondary labels)
- **Text Faint:** `#71717a` (Footers, helper text, timestamps)
- **Accent Primary:** `#3b82f6` (Single focal accent for primary actions and active tabs)
- **Accent Contrast:** `#ffffff` (Text on top of accent fill)

*Palette Rules:*
- Max 1 accent color with saturation < 80%.
- No AI purple/neon glow aesthetic.
- Color consistency lock: the same accent must apply across the entire page.

---

## 3. Typography Architecture
- **Display / Headlines:** `Geist Display` or `Cabinet Grotesk`, sans-serif
  - Tracking: `tracking-tighter`
  - Leading: `leading-none` or `leading-[1.1]`
  - Scale: `text-4xl sm:text-5xl lg:text-6xl`
- **Body & Subtitles:** `Geist Sans` or `Satoshi`, sans-serif
  - Tracking: `tracking-normal`
  - Leading: `leading-relaxed`
  - Reading Width: `max-w-[65ch]`
  - Scale: `text-base` or `text-lg`
- **Code & Numbers:** `Geist Mono` or `JetBrains Mono`, monospace
  - Feature: `font-variant-numeric: tabular-nums` for data columns and timers.
- **Serif Discipline:** Serif is banned as default. If explicitly requested for an editorial brand, use `PP Editorial New` or `GT Sectra`.

---

## 4. Component Stylings & Behaviors
- **Buttons:**
  - Primary: `bg-accent text-white px-5 py-2.5 rounded-lg font-medium transition-transform active:scale-[0.98]`
  - Secondary: `bg-surface border border-border-subtle text-text-high-contrast px-5 py-2.5 rounded-lg font-medium hover:bg-surface-elevated`
  - Contrast check: Text must pass WCAG AA (4.5:1 min) against button background.
  - No text wrapping on desktop buttons.
- **Cards & Bento Grid:**
  - Corner radius: Uniform `rounded-xl` (`16px`).
  - Dividers: 1px subtle borders over heavy drop shadows.
  - Diversity: Bento cells must include visual variance (interactive previews, charts, photography), not plain text cards.
- **Forms & Inputs:**
  - Labels always above inputs (`text-sm font-medium text-text-muted mb-1.5`).
  - Inputs: `bg-surface border border-border-subtle rounded-lg px-3.5 py-2 text-text-high-contrast`
  - Focus state: `focus-visible:ring-2 focus-visible:ring-accent focus-visible:outline-none`
  - Inline errors rendered beneath inputs in red (`text-red-400 text-xs mt-1`).
- **Feedback & Loading:**
  - Skeletal shimmer matching component geometry. Circular spinners banned.

---

## 5. Layout & Spatial Discipline
- **Containment:** `max-w-7xl mx-auto px-4 sm:px-6 lg:px-8`
- **Section Rhythm:** `py-20 md:py-32` vertical padding.
- **Hero Viewport Discipline:**
  - Max top padding: `pt-24` desktop.
  - Headline max 2 lines, subtext max 20 words, CTA visible without scroll (`min-h-[100dvh]`).
  - Max 4 text elements total.
- **Eyebrow Restraint:** Max 1 uppercase eyebrow label per 3 sections.
- **Zigzag Cap:** Max 2 consecutive left-image/right-text split rows.

---

## 6. Responsive Rules (< 768px)
- Multi-column layouts must collapse to a single column below 768px.
- Minimum touch target: `44px × 44px`.
- Set `touch-action: manipulation` on buttons.
- Zero horizontal overflow.

---

## 7. Motion & Physics
- **Engine:** Motion (`motion/react`) for UI states; GSAP for pinned scroll stacks.
- **Spring Physics:** `stiffness: 100, damping: 20`.
- **Reduced Motion:** Always honor `prefers-reduced-motion: reduce`.

---

## 8. Anti-Patterns & Banned AI Tells
- ZERO em-dashes (`—`) anywhere across headlines, eyebrows, buttons, or body.
- No purple or neon button glows.
- No 3-column equal feature card repeats.
- No fake div-based screenshot slop.
- No unmotived serif fonts (`Fraunces` and `Instrument Serif` are banned).
- No generic AI marketing buzzwords ("Elevate", "Seamless", "Next-Gen", "Unleash").
