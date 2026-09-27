---
name: ui-design
description: Elite UI/UX design & frontend engineering skill. Combines anti-slop visual taste, the 38 anti-slop rules & craftsmanship standards, DESIGN.md system contracts, image-first design generation, Vercel web interface guidelines, and autonomous Playwright visual verification.
metadata:
  author: ravizikrillah
  version: "1.1.0"
  argument-hint: "[brief | file-or-pattern | design-md | screenshot | audit]"
---

# UI Design Skill: The Unified Design & Frontend Engineering Engine

An end-to-end frontend craft engine for AI coding agents. It unifies six battle-tested design and engineering methodologies:

1. **Anti-Slop Visual Taste & The Three Dials** (from `Leonxlnx/taste-skill`) — eliminates generic AI layouts, centered dark clichés, and purple neon glows with disciplined art direction.
2. **The 38 Anti-Slop Rules & Craftsmanship Standard** (from `miqdadbadjuber/anti-slop`) — enforces the 3-tier rule filter (Hard Gate, Purpose-Gate, Quality Locks), C-1 to C-5 craftsmanship criteria, and dual-mode execution (Mode 1: During vs Mode 2: After/Audit).
3. **Declarative Design System Contracts** (from `voltagent/awesome-design-md` & `getdesign.md`) — single-source-of-truth `DESIGN.md` specification for tokens, atmospheric dials, and anti-patterns.
4. **Image-to-Code Workflow** (from `image-to-code-skill`) — image-first section generation, deep visual extraction, and faithful translation for visually demanding web interfaces.
5. **Vercel Web Interface Guidelines** (from `vercel-labs/agent-skills`) — uncompromising accessibility (WCAG AA/AAA), keyboard focus states, form engineering, hydration safety, and Core Web Vitals.
6. **Autonomous Playwright Verification Loop** (from `microsoft/playwright-cli`) — token-efficient headless browser snapshots, multi-viewport screenshot verification, and automated visual regression checks.

---

## The Two Usage Modes

At initialization or when prompted, determine the operating mode:

* **Mode 1 (During Build):** Follow all anti-slop rules, design contracts, and guidelines actively during generation and styling. Enforce the Delivery Gate before hand-off.
* **Mode 2 (After Build / Audit):** Perform a comprehensive audit on an existing interface. Generate a numbered audit report (`anti-slop/audit-001-YYYY-MM-DD.md`) prioritizing Hard Gate (HIGH), Purpose-Gate (MEDIUM), and Quality Locks (LOW). Require user approval before making changes.

---

## The 5-Phase Workflow

When building, redesigning, or auditing UI, follow these phases sequentially:

```
┌─────────────────────────────────────────────────────────────┐
│  Phase 0: Mode Selection, Brief Inference & The Dials       │
│  • Select Mode 1 (During) or Mode 2 (Audit)                 │
│  • Infer page kind, audience, vibe words, quiet constraints │
│  • Calibrate The Three Dials (Variance / Motion / Density)  │
│  • Output 1-line Design Read before code                    │
└──────────────────────────────┬──────────────────────────────┘
                               │
                               ▼
┌─────────────────────────────────────────────────────────────┐
│  Phase 1: Design Contract & DESIGN.md                       │
│  • Read existing DESIGN.md OR generate a tailored one       │
│  • Select official design system package or aesthetic family│
└──────────────────────────────┬──────────────────────────────┘
                               │
                               ▼
┌─────────────────────────────────────────────────────────────┐
│  Phase 2: Visual Grounding (Image-to-Code)                  │
│  • For visual pages: Generate standalone section images     │
│  • Perform deep visual analysis (tokens, spatial rhythm)    │
└──────────────────────────────┬──────────────────────────────┘
                               │
                               ▼
┌─────────────────────────────────────────────────────────────┐
│  Phase 3: Frontend Implementation                           │
│  • Apply Tier 1 Hard Gates (no em-dash, no dead buttons)    │
│  • Apply Tier 2 Purpose-Gates & Tier 3 Quality Locks        │
│  • Enforce Vercel Web Interface Guidelines (a11y, forms)    │
└──────────────────────────────┬──────────────────────────────┘
                               │
                               ▼
┌─────────────────────────────────────────────────────────────┐
│  Phase 4: Autonomous Playwright Verification                │
│  • Open headless page via @playwright/cli                   │
│  • Capture token-efficient DOM & a11y snapshots             │
│  • Capture multi-viewport screenshots (375, 768, 1440px)    │
│  • Run contrast & overflow checks; auto-fix discrepancies   │
└──────────────────────────────┬──────────────────────────────┘
                               │
                               ▼
┌─────────────────────────────────────────────────────────────┐
│  Phase 5: Delivery Gate & Keystone Test                     │
│  • Run Logo-Swap Keystone Test ("Does it feel unique?")     │
│  • Execute 25-point non-negotiable verification matrix      │
└─────────────────────────────────────────────────────────────┘
```

---

## Phase 0: Brief Inference & The Three Dials

Before touching any code or creating visual assets, **read the room**:

### 0.A Read Key Signals
1. **Page Kind:** SaaS landing, creative studio, consumer product, portfolio, editorial, public sector.
2. **Vibe Words:** "minimalist", "editorial", "Linear-style", "brutalist", "Apple-y", "hacker / dark-tech", "playful".
3. **Audience:** B2B procurement, design-conscious consumer, developer, recruiter.
4. **Quiet Constraints:** WCAG compliance, public sector trust, dark mode requirement, mobile-first.

### 0.B The Three Dials Configuration
Set the three core dials (`1-10` scale):
* **`DESIGN_VARIANCE`** (1 = Rigid / Conventional, 10 = Artsy Chaos / Asymmetric)
* **`MOTION_INTENSITY`** (1 = Static / Restrained, 10 = Cinematic / Physics-driven)
* **`VISUAL_DENSITY`** (1 = Art Gallery Airy, 10 = Cockpit / Data-packed)

#### Baseline Presets
| Use Case | VARIANCE | MOTION | DENSITY |
|---|---|---|---|
| Modern SaaS Landing | 7 | 6 | 4 |
| Creative Studio / Agency | 9 | 8 | 3 |
| Premium Consumer (DTC) | 7 | 6 | 3 |
| Developer Portfolio | 6 | 5 | 4 |
| Designer Portfolio | 8 | 7 | 3 |
| Editorial / Publication | 6 | 4 | 3 |
| B2B Enterprise / Public Sector | 3 | 2 | 5 |

### 0.C Mandatory One-Line "Design Read"
Before writing any code or markdown, output a single line:
> **"Reading this as: `<page kind>` for `<audience>`, with a `<vibe>` language, leaning toward `<design system or aesthetic family>`."**

---

## Phase 1: Declarative Design System (`DESIGN.md`)

Every project must be guided by a clear design contract.

1. **Check for `DESIGN.md`:** Look in the project root for an existing `DESIGN.md`. If found, adopt its tokens, typography, and constraints.
2. **Generate `DESIGN.md` if Missing:** If none exists, generate one based on `templates/DESIGN.md` before coding. (R-37: Never design without direction; if unavailable, label as *"draft without direction"*).
3. **Pick Foundation (Official Package vs Aesthetic):**
   * **Enterprise SaaS / Analytics:** `@fluentui/react-components`, `@carbon/react`, or `@primer/react-brand`.
   * **Accessible React Foundation:** `@radix-ui/themes` or `shadcn/ui`.
   * **Tailwind-first Modern Web:** Tailwind CSS v4 + native CSS variables.
   * **Aesthetic Directions (Bento, Glassmorphism, Brutalism):** Implement with native CSS + Tailwind.

---

## Phase 2: Visual Grounding (Image-to-Code Workflow)

When visual quality is critical (landing pages, heroes, portfolios, showcase sites):

1. **Image Generation First:**
   * If an image generation tool is available (`generate_image`, Imagen, DALL-E, Midjourney), generate **dedicated standalone images per section**.
   * **Never** generate one single compressed collage where text and details become blurry.
   * **Never** crop low-res fragments from full-page mockups.
2. **Deep Visual Extraction:**
   * Extract color tokens (canvas background, surface fills, single high-contrast accent).
   * Extract typographic hierarchy (display scale, leading, letter-spacing).
   * Extract spatial rhythm (padding, gap dimensions, grid proportions).
   * Extract button anatomy (corner radius, padding, elevation, tactile states).
3. **Code Translation:**
   * Build the UI directly matching the extracted visual truth.

---

## Phase 3: Frontend Implementation & 3-Tier Anti-Slop Rules

### 3.1 Tier 1: Hard Gate Rules (Non-Negotiable)
* **Zero Em-Dashes (R-02):** Ban `—` anywhere in copy written by the agent. Use commas, colons, or clean phrasing.
* **Mobile Responsiveness (R-03):** 44px min tap targets, no horizontal overflow, clean mobile navigation.
* **No Fabricated Data or Testimonials (R-17, R-18, R-36):** Never invent metrics ("99.9% uptime") or fake avatars/reviews. Use real data or explicit placeholders (`[REAL DATA]`).
* **Functional Elements Only (R-26):** Every button and link must perform an action or navigate to a real section. Dead controls are banned.
* **Three UI States (R-27):** Every data component must implement **Empty**, **Loading**, and **Error** states.
* **Keyboard Accessibility (R-32):** Tab/Shift-Tab navigation, visible focus rings (`focus-visible:ring-2`), and Escape key handlers for dialogs.

### 3.2 Tier 2: Purpose-Gate Rules (Technique Allowed, Stated Purpose Required)
* **Color & Gradients (R-01):** AI purple/neon glow is banned as a default. Permitted only if part of verified brand identity.
* **Relevant Icons (R-04):** Banned generic sparkle/star/magic/robot AI icons. Use content-relevant glyphs only.
* **Glassmorphism Dose Cap (R-10):** Accent on max 1–2 elements. Banned on navbar, cards, modals, and sidebars at once.
* **Glow Dose Cap (R-13):** Accent on max 1–2 key elements.
* **Feature Cards Variance (R-14):** Cards must reflect content hierarchy, not 6 identical cloned boxes.
* **Motivated Animation (R-19):** Every motion must guide attention or communicate state. No decorative loop chaos.

### 3.3 Tier 3: Quality Locks & Vercel Guidelines
* **Content-Driven Structure (R-05):** Reject AI template layouts (Hero + 3 cards + 3-step "How it works" + 3 pricing cards).
* **Specific CTAs (R-15):** Contextual labels ("Start Free Trial", "View Live Demo") over generic "Get Started".
* **Banned Buzzwords (R-16):** Reject "AI-Powered", "Next-Gen", "Seamless", "Revolutionary", "Cutting-Edge".
* **Vercel Usability Standards:**
  * Icon-only buttons must have `aria-label`.
  * Inline form validation beneath inputs; non-blocking paste (`onPaste` preventDefault banned).
  * Explicit `width` and `height` on images to eliminate CLS.
  * `color-scheme: dark` on root `<html>` for dark mode stability.

---

## Phase 4: Autonomous Playwright Verification Loop

Perform autonomous browser verification with `@playwright/cli`:

```bash
# 1. Start local dev server (if not already running)
npm run dev &

# 2. Launch browser session
npx @playwright/cli open http://localhost:3000

# 3. Take accessibility & DOM snapshot
npx @playwright/cli snapshot

# 4. Capture responsive screenshots across viewports
npx @playwright/cli screenshot --viewport-size 1440,900 --full-page --output .playwright/desktop.png
npx @playwright/cli screenshot --viewport-size 768,1024 --full-page --output .playwright/tablet.png
npx @playwright/cli screenshot --viewport-size 375,667 --full-page --output .playwright/mobile.png

# 5. Close session when verified
npx @playwright/cli close
```

*Auto-Audit Checklist:*
1. Inspect DOM snapshot for unlabelled buttons or inputs.
2. Inspect `.playwright/desktop.png` and `.playwright/mobile.png` for layout balance.
3. Check for horizontal overflow (`scrollWidth > clientWidth`).
4. Verify visible focus rings during keyboard navigation.

---

## Phase 5: Delivery Gate & Keystone Test

Before declaring any design task complete, verify every item:

### The Keystone Question:
> **"If the logo and product name were swapped out, would this design still feel unique and have its own character?"**

### Pre-Flight Matrix:
- [ ] **Mode 1 or Mode 2** executed correctly?
- [ ] **Brief Inference declared** in a clear one-line Design Read?
- [ ] **The Three Dials** explicitly configured and aligned with the brief?
- [ ] **DESIGN.md** consulted or generated at project root?
- [ ] **ZERO em-dashes (`—`)** anywhere on the page? (R-02)
- [ ] **Page Theme Lock:** One cohesive theme across all sections (no mid-page inversions)?
- [ ] **Color Consistency Lock:** Exactly one accent color (<80% sat) locked across the entire page?
- [ ] **Anti-Purple Check:** No generic purple/neon gradient buttons or glows? (R-01)
- [ ] **Shape Consistency:** Uniform corner-radius scale across buttons, cards, and inputs? (R-11)
- [ ] **Typography Discipline:** Sans display by default; no `Inter` for creative briefs; no unmotivated serifs?
- [ ] **Hero Fits Viewport:** Headline ≤ 2 lines, subtext ≤ 20 words, CTAs visible without scroll?
- [ ] **Hero Top Padding Cap:** Max `pt-24` desktop?
- [ ] **Eyebrow Count:** Mechanical count ≤ `ceil(sections / 3)`?
- [ ] **Functional Elements Only:** Every button, link, and toggle works or is removed? (R-26)
- [ ] **No Fabricated Claims:** Zero fake stats, fake testimonials, or fake compliance logos? (R-17, R-18, R-36)
- [ ] **Three UI States:** Data components include Empty, Loading, and Error states? (R-27)
- [ ] **WCAG AA Contrast:** Text passes 4.5:1; button text passes against button backgrounds? (R-25)
- [ ] **CTA Button Wrap:** No desktop button label wraps to 2+ lines?
- [ ] **Visible Focus States:** All interactive elements feature `focus-visible:ring-2`? (R-32)
- [ ] **Form Labels:** Explicit labels above inputs; non-blocking paste; inline errors below?
- [ ] **Touch Targets:** Minimum 44px on mobile; `touch-action: manipulation` applied? (R-03)
- [ ] **Mobile Collapse:** Explicit single-column fallback on `< 768px`; zero horizontal scrollbar bugs?
- [ ] **Playwright Verification:** DOM snapshot inspected; responsive screenshots reviewed? (R-35)
