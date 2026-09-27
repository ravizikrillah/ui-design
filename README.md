# UI Design (`ui-design`)

[![Skills.sh Compatible](https://img.shields.io/badge/skills.sh-compatible-10b981?style=flat-square)](https://skills.sh)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg?style=flat-square)](LICENSE)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](https://github.com/Ravizikrillah/ui-design/pulls)

An elite, unified UI/UX design and frontend engineering skill for AI coding agents (Claude Code, Cursor, Windsurf, Codex, Antigravity, and Gemini CLI).

It eliminates the generic, uninspired output typical of AI-generated frontends by synthesizing six leading design, auditing, and engineering methodologies into one cohesive workflow.

---

## ⚡ Instant Installation

Install directly into your AI coding assistant with the [skills.sh](https://skills.sh) CLI:

```bash
npx skills add Ravizikrillah/ui-design
```

Or install via specific skill flag:
```bash
npx skills add Ravizikrillah/ui-design --skill ui-design
```

---

## 🧠 The 6 Unified Pillars

This skill merges and refines six battle-tested resources:

```
┌────────────────────────────────────────────────────────────────────────┐
│                        UI DESIGN SKILL ENGINE                          │
├──────────────────┬──────────────────┬──────────────────────────────────┤
│ 1. Taste Skill   │ 2. Anti-Slop     │ 3. DESIGN.md                     │
│ (Anti-Slop Core) │ (Rules R-01..38) │ (VoltAgent Spec)                 │
├──────────────────┼──────────────────┼──────────────────────────────────┤
│ 4. Image-to-Code │ 5. Web Interface │ 6. Playwright CLI                │
│ (Visual-First)   │ (Vercel a11y)    │ (Autonomous Verification)        │
└──────────────────┴──────────────────┴──────────────────────────────────┘
```

1. **Anti-Slop Visual Taste & The Three Dials** (from [`Leonxlnx/taste-skill`](https://github.com/Leonxlnx/taste-skill))
   * **The Three Dials:** Dynamic calibration of `DESIGN_VARIANCE`, `MOTION_INTENSITY`, and `VISUAL_DENSITY`.
   * **Brief Inference:** Reading the room before touching code. Outputs a mandatory 1-line "Design Read".
   * **Anti-Default Discipline:** Bans centered dark heroes, generic purple neon glows, AI clichés, and unmotivated serif typography.

2. **The 38 Anti-Slop Rules & Craftsmanship Standard** (from [`miqdadbadjuber/anti-slop`](https://github.com/miqdadbadjuber/anti-slop))
   * **3-Tier Rule Filter:**
     * **Hard Gate (R-02, R-03, R-17, R-18, R-23..R-38):** Non-negotiable absolute gates (Zero em-dashes, mobile perfection, no dead buttons, no fabricated stats/claims).
     * **Purpose-Gate (R-01, R-04..R-22):** Allowed only when serving verified hierarchy or brand identity with a written rationale.
     * **Quality Locks (R-05, R-11..R-31):** Consistency locks across radii, copywriting, and the Keystone Logo-Swap Test.
   * **Craftsmanship Standard:** C-1 Intentionality, C-2 Functional Completeness, C-3 Content-Driven Composition, C-4 Resilience, C-5 Evidence Over Claims.
   * **Two Operational Modes:** Mode 1 (During Build) and Mode 2 (After Build / Audit with numbered markdown reports).

3. **Declarative Design System Contracts** (from [`voltagent/awesome-design-md`](https://github.com/voltagent/awesome-design-md) & [`getdesign.md`](https://getdesign.md))
   * Standardizes the single-source-of-truth `DESIGN.md` specification at your repository root.
   * Codifies theme atmosphere, color tokens, typography scale, component rules, and anti-patterns into agent-readable markdown.

4. **Image-to-Code Workflow** (from [`taste-skill/image-to-code-skill`](https://github.com/Leonxlnx/taste-skill/blob/main/skills/image-to-code-skill/SKILL.md))
   * Enforces an **image-first** methodology for visually demanding web interfaces.
   * Generates dedicated standalone section references rather than blurry full-page collages.
   * Deep visual extraction: inspects spatial rhythm, color tokens, and button anatomy before coding.

5. **Vercel Web Interface Guidelines** (from [`vercel-labs/agent-skills`](https://github.com/vercel-labs/agent-skills))
   * **Accessibility:** WCAG AA/AAA contrast (4.5:1 min), semantic HTML `<button>`/`<a>`/`<label>`, aria-live feedback.
   * **Focus States:** High-contrast `focus-visible:ring-2` on all interactive elements; no unreplaced `outline-none`.
   * **Form Ergonomics:** Labels above inputs, non-blocking paste, inline error positioning, and autocomplete optimization.
   * **Performance:** Eliminates Cumulative Layout Shift (CLS) with explicit image sizing and fetch priorities.

6. **Autonomous Playwright Verification** (from [`microsoft/playwright-cli`](https://github.com/microsoft/playwright-cli))
   * Closes the loop on AI development by having the agent verify its own work in a headless browser session.
   * Token-efficient element snapshots (`playwright-cli snapshot`) for rapid structural and accessibility verification.
   * Multi-viewport screenshot captures (`375px`, `768px`, `1440px`) to verify visual alignment and catch horizontal overflow bugs automatically.

---

## 🚀 The 5-Phase Workflow

When an agent executes this skill, it follows a strict 5-phase loop:

```
[ Phase 0: Mode Selection (During/Audit) & Brief Inference ]
                              │
                              ▼
[ Phase 1: Declarative DESIGN.md System Selection ]
                              │
                              ▼
[ Phase 2: Visual Grounding (Image Generation & Extraction) ]
                              │
                              ▼
[ Phase 3: Frontend Implementation (Tailwind v4, RSC, Motion, 3-Tier Anti-Slop) ]
                              │
                              ▼
[ Phase 4: Autonomous Playwright Verification & Multi-Viewport Audit ]
                              │
                              ▼
[ Phase 5: Keystone Logo-Swap Test & Delivery Gate ]
```

---

## 📂 Repository Structure

```
ui-design/
├── SKILL.md                          # Root skill manifest for instant `npx skills add`
├── skills/
│   └── ui-design/
│       └── SKILL.md                  # Monorepo / sub-path skill entry
├── templates/
│   └── DESIGN.md                     # Ready-to-use DESIGN.md starter template
├── references/
│   ├── anti-slop-rules.md            # Complete 38-rule catalog, C1-C5 standards, & dual-mode audit guide
│   ├── web-interface-guidelines.md   # Vercel a11y, form ergonomics, & performance rules
│   ├── image-to-code-workflow.md     # 3-phase image generation & visual extraction guide
│   ├── design-md-specification.md    # Specification for writing and reading DESIGN.md files
│   └── playwright-verification.md    # Autonomous browser auditing with @playwright/cli
├── README.md                         # Project documentation
└── LICENSE                           # MIT License
```

---

## 🧪 Playwright CLI Testing Flow

Agents equipped with this skill can run automated verification on local servers:

```bash
# 1. Open persistent headless session
npx @playwright/cli open http://localhost:3000

# 2. Capture token-efficient DOM snapshot for a11y review
npx @playwright/cli snapshot

# 3. Capture responsive screenshots across viewports
npx @playwright/cli screenshot --viewport-size 1440,900 --full-page --output .playwright/desktop.png
npx @playwright/cli screenshot --viewport-size 375,667 --full-page --output .playwright/mobile.png

# 4. Close session
npx @playwright/cli close
```

---

## 📋 Delivery Gate Checklist

Before any design task is declared complete, the agent verifies:

- [x] **Mode 1 or Mode 2** executed correctly.
- [x] **Keystone Logo-Swap Test:** Does the interface feel unique if the logo and name are swapped?
- [x] **Design Read** declared in one clear sentence.
- [x] **The Three Dials** calibrated to project intent.
- [x] **`DESIGN.md`** established at project root.
- [x] **ZERO em-dashes (`—`)** anywhere in copy (R-02).
- [x] **Page Theme Locked:** No mid-scroll theme inversion.
- [x] **Single Accent Color:** Saturation < 80%, consistent across all sections.
- [x] **Anti-Purple Rule:** No generic purple/neon button glows (R-01).
- [x] **Hero Viewport Fit:** Fits `100dvh` without scroll; headline ≤ 2 lines; subtext ≤ 20 words.
- [x] **Eyebrow Restraint:** Max 1 eyebrow per 3 sections.
- [x] **WCAG AA Contrast:** 4.5:1 min for text, buttons, and inputs (R-25).
- [x] **Functional Controls Only:** Every button and link performs an actual action or navigates to an existing section (R-26).
- [x] **No Fabricated Claims:** Zero fake stats or fictional testimonials (R-17, R-18, R-36).
- [x] **Three UI States:** Data components include Empty, Loading, and Error states (R-27).
- [x] **Button Wrap Check:** No wrapped button text on desktop.
- [x] **Form Labels:** Explicit labels above inputs; non-blocking paste.
- [x] **Mobile Collapse:** Clean single-column layout `< 768px`; zero horizontal scrollbar bugs (R-03).
- [x] **Playwright Audit:** Screenshots and DOM snapshots reviewed (R-35).

---

## 📄 License

MIT © [Ravi Zikrillah](https://github.com/Ravizikrillah)
