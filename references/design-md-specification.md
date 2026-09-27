# DESIGN.md Specification & Architecture

This reference defines the `DESIGN.md` specification originated by Google Stitch and curated by VoltAgent's `awesome-design-md` and `getdesign.md`.

A `DESIGN.md` file is a plain-text markdown design system contract placed at the root of a project. It serves as the single source of truth for AI design agents to ensure visual consistency, prevent AI tells, and unify brand design tokens across all components.

---

## 1. Why DESIGN.md?

* **Agent-Native:** Markdown is the most reliable format for LLMs to ingest and adhere to.
* **No Figma or JSON Bloat:** Eliminates large, complex design token JSON schemas or heavy image files.
* **Single Source of Truth:**
  * `AGENTS.md` / `CLAUDE.md` → Tells the agent *how to build* the codebase.
  * `DESIGN.md` → Tells the agent *how the UI should look and feel*.

---

## 2. Mandatory File Structure

A compliant `DESIGN.md` must contain the following 8 sections:

```markdown
# Design System: [Project / Brand Name]

## 1. Visual Theme & Atmosphere
- **Aesthetic Direction:** [e.g. Linear-style Minimalist Dark Tech / Editorial Swiss / Apple-y Clean]
- **Density:** [1-10] (e.g., 4 — Balanced, airy whitespace)
- **Variance:** [1-10] (e.g., 7 — Asymmetric layouts, offset rhythm)
- **Motion:** [1-10] (e.g., 6 — Restrained spring physics, micro-interactions)

## 2. Color Palette & Roles
- **Canvas:** `#09090b` (Primary page background)
- **Surface:** `#18181b` (Card, modal, and panel backgrounds)
- **Surface Muted:** `#27272a` (Secondary borders, subtle dividers)
- **Text Primary:** `#fafafa` (Headings, primary labels)
- **Text Muted:** `#a1a1aa` (Body copy, metadata, timestamps)
- **Accent:** `#3b82f6` (Single focal accent for primary CTAs and active states)
- **Accent Contrast:** `#ffffff` (Text label inside accent button)
- *(Rule: Maximum 1 accent color. Saturation < 80%. No generic AI purple gradients.)*

## 3. Typography Rules
- **Display / Headings:** `Geist`, sans-serif. Tracking: `tracking-tight`. Line height: `leading-tight`.
- **Body:** `Geist`, sans-serif. Tracking: `tracking-normal`. Line height: `leading-relaxed`. Max reading length: `65ch`.
- **Monospace:** `Geist Mono` or `JetBrains Mono` for code snippets, tabular metrics, and timestamps.
- **Rules:**
  * Sans display by default.
  * No `Inter` for creative or high-variance briefs.
  * No unmotivated serifs (`Fraunces` and `Instrument Serif` are banned as generic reach).
  * Headline italic words with descenders (`y, g, j, p, q`) must include bottom padding and `leading-[1.15]`.

## 4. Component Stylings
- **Buttons:**
  * Primary: Accent fill, bold label, tactile `-translate-y-px` on hover, `scale-[0.98]` on active.
  * Secondary / Outline: 1px border (`border-white/10`), surface background, high-contrast text.
  * Uniform radius: Pill (`rounded-full`) or soft rectangle (`rounded-lg`).
- **Cards & Bento Cells:**
  * Background: Surface with subtle 1px border.
  * Elevation: Soft diffused ambient shadow tinted to background hue.
  * Padding: Generous interior padding (`p-6 md:p-8`).
- **Forms & Inputs:**
  * Label always positioned above input.
  * Background: `bg-zinc-900/60`, border: `border-zinc-800`.
  * Focus state: `focus-visible:ring-2 focus-visible:ring-accent`.
- **Feedback & Loaders:**
  * Skeletal shimmer matching the layout shape. No generic circular spinners.

## 5. Layout & Spatial Principles
- **Grid Architecture:** CSS Grid over complex Flexbox percentage hacks.
- **Max Width Containment:** `max-w-7xl mx-auto px-4 sm:px-6 lg:px-8`.
- **Section Spacing:** Generous vertical padding (`py-20 md:py-32`).
- **Hero Discipline:**
  * Fits initial viewport (`min-h-[100dvh]`).
  * Headline max 2 lines desktop, subtext max 20 words.
  * Max 4 text elements total.

## 6. Responsive Rules (< 768px)
- **Column Collapse:** All multi-column layouts must collapse to a single column below 768px.
- **Touch Targets:** Minimum 44px tap targets for all mobile controls.
- **Zero Horizontal Scroll:** Prevent any horizontal scrollbar overflow.

## 7. Motion & Physics
- **Engine:** Motion (`motion/react`) for UI interactions; GSAP for complex scroll-pinned sequences.
- **Spring Physics:** `type: "spring", stiffness: 100, damping: 20`.
- **Reduced Motion:** Always honor `prefers-reduced-motion: reduce`.

## 8. Explicit Anti-Patterns & Banned AI Tells
- ZERO em-dashes (`—`) anywhere in copy or UI labels.
- No AI purple/violet button glow aesthetic.
- No 3-column equal feature card rows repeated across sections.
- No fake div-based screenshot slop.
- No wrapped CTA buttons on desktop.
- No generic AI marketing buzzwords ("Elevate", "Seamless", "Next-Gen", "Unleash").
```

---

## 3. How Agents Use DESIGN.md

1. **At Initialization:** The agent checks if `DESIGN.md` exists. If so, it reads the file and locks its variables (`Canvas`, `Accent`, `Typography`, `Radii`).
2. **Scaffolding:** When starting a new greenfield project without a design system, the agent creates `DESIGN.md` first, presents the tokens to the user, and proceeds with implementation.
3. **During Code Reviews:** The agent validates code diffs against the `DESIGN.md` rules (ensuring no rogue colors, unapproved fonts, or banned layouts were introduced).
