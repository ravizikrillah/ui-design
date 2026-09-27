# 🎨 UI Design (`@ravizikrillah/ui-design`)

[![skills.sh](https://img.shields.io/badge/skills.sh-ravizikrillah%2Fui--design-blue?style=flat-square)](https://www.skills.sh/ravizikrillah/ui-design/ui-design)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](https://opensource.org/licenses/MIT)
[![PRs Welcome](https://img.shields.io/badge/PRs-welcome-brightgreen.svg?style=flat-square)](https://github.com/ravizikrillah/ui-design/pulls)

> **Universal UI/UX Design & Frontend Engineering Engine for AI Agents.**  
> Eliminates generic AI defaults, purple neon glows, and slop interfaces by synthesizing six battle-tested methodologies: anti-slop visual taste, the 38-rule 3-tier filter, declarative `DESIGN.md` contracts, image-first section translation, Vercel web guidelines (a11y/forms/performance), and autonomous Playwright visual verification.

🌐 **Skills Directory Page**: [https://www.skills.sh/ravizikrillah/ui-design/ui-design](https://www.skills.sh/ravizikrillah/ui-design/ui-design)

---

## 🚀 Installation & Quickstart

### Option A: Install Globally (User-Level for all your projects)
Installs skills into `~/.agents/skills/` accessible across all repositories and AI coding agents on your machine:
```bash
npx skills add ravizikrillah/ui-design -g
```

### Option B: Install at Project Level (Shared via Git for All Teammates)
Installs skills directly into your project's `.agents/skills/` using physical file copying (`--copy` prevents broken symlinks across machines). When committed to Git, **anyone who pulls or clones your project repository can immediately use the UI Design skill without installing anything**:
```bash
# 1. Install skill at project level
npx skills add ravizikrillah/ui-design --copy

# 2. Commit to Git so all teammates inherit the skill
git add .agents/ skills-lock.json
git commit -m "feat: install ui-design skill at project level"
git push origin main
```

### Option C: Multi-Agent Compatibility
The skill automatically configures itself for your active agent runtime:
* **Claude Code:** Automatically copied to `.claude/skills/ui-design`
* **Cursor:** Compatible with `.cursorrules` and Cursor Agent
* **Windsurf:** Integrates directly into `.windsurfrules`
* **Codex / Antigravity / Gemini CLI:** Discovered via `.agents/skills/ui-design`

---

## 🧠 The 6 Unified Pillars

This skill merges and refines six industry-leading frontend and design engineering standards:

```text
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

### 1. Anti-Slop Visual Taste & The Three Dials ([`Leonxlnx/taste-skill`](https://github.com/Leonxlnx/taste-skill))
* **The Three Dials:** Dynamic calibration of `DESIGN_VARIANCE`, `MOTION_INTENSITY`, and `VISUAL_DENSITY` (scale 1–10).
* **Brief Inference:** Reads the room before touching code. Outputs a mandatory 1-line *"Design Read"*.
* **Anti-Default Discipline:** Bans centered dark heroes, generic purple neon glows, AI clichés, and unmotivated serif typography.

### 2. The 38 Anti-Slop Rules & Craftsmanship Standard ([`miqdadbadjuber/anti-slop`](https://github.com/miqdadbadjuber/anti-slop))
* **3-Tier Rule Filter:**
  * **Hard Gate (R-02, R-03, R-17, R-18, R-23..R-38):** Non-negotiable absolute gates (Zero em-dashes, mobile perfection, no dead buttons, no fabricated stats/claims).
  * **Purpose-Gate (R-01, R-04..R-22):** Allowed only when serving verified hierarchy or brand identity with a written rationale.
  * **Quality Locks (R-05, R-11..R-31):** Consistency locks across radii, copywriting, and the Keystone Logo-Swap Test.
* **Craftsmanship Standard:** C-1 Intentionality, C-2 Functional Completeness, C-3 Content-Driven Composition, C-4 Resilience, C-5 Evidence Over Claims.
* **Two Operational Modes:** Mode 1 (During Build) and Mode 2 (After Build / Audit with numbered markdown reports).

### 3. Declarative Design System Contracts ([`voltagent/awesome-design-md`](https://github.com/voltagent/awesome-design-md) & [`getdesign.md`](https://getdesign.md))
* Standardizes the single-source-of-truth `DESIGN.md` specification at your repository root.
* Codifies theme atmosphere, color tokens, typography scale, component rules, and anti-patterns into agent-readable markdown.

### 4. Image-to-Code Workflow ([`taste-skill/image-to-code-skill`](https://github.com/Leonxlnx/taste-skill/blob/main/skills/image-to-code-skill/SKILL.md))
* Enforces an **image-first** methodology for visually demanding web interfaces.
* Generates dedicated standalone section references rather than blurry full-page collages.
* Deep visual extraction: inspects spatial rhythm, color tokens, and button anatomy before coding.

### 5. Vercel Web Interface Guidelines ([`vercel-labs/agent-skills`](https://github.com/vercel-labs/agent-skills))
* **Accessibility:** WCAG AA/AAA contrast (4.5:1 min), semantic HTML `<button>`/`<a>`/`<label>`, aria-live feedback.
* **Focus States:** High-contrast `focus-visible:ring-2` on all interactive elements; no unreplaced `outline-none`.
* **Form Ergonomics:** Labels above inputs, non-blocking paste, inline error positioning, and autocomplete optimization.
* **Performance:** Eliminates Cumulative Layout Shift (CLS) with explicit image sizing and fetch priorities.

### 6. Autonomous Playwright Verification ([`microsoft/playwright-cli`](https://github.com/microsoft/playwright-cli))
* Closes the loop on AI development by having the agent verify its own work in a real headless browser session.
* Token-efficient element snapshots (`playwright-cli snapshot`) for rapid structural and accessibility verification.
* Multi-viewport screenshot captures (`375px`, `768px`, `1440px`) to verify visual alignment and catch horizontal overflow bugs automatically.

---

## ⚡ The 5-Phase Workflow

When an agent executes this skill, it follows a strict 5-phase execution pipeline:

```text
┌─────────────────────────────────────────────────────────────┐
│  Phase 0: Mode Selection (During/Audit) & Brief Inference   │
│  • Select Mode 1 (During) or Mode 2 (Audit)                 │
│  • Infer page kind, audience, vibe words, quiet constraints │
│  • Calibrate The Three Dials (Variance / Motion / Density)  │
│  • Output 1-line Design Read before code                    │
└──────────────────────────────┬──────────────────────────────┘
                               │
                               ▼
┌─────────────────────────────────────────────────────────────┐
│  Phase 1: Design Contract & DESIGN.md Selection             │
│  • Read existing DESIGN.md OR scaffold a tailored one       │
│  • Select official design system package or aesthetic family│
└──────────────────────────────┬──────────────────────────────┘
                               │
                               ▼
┌─────────────────────────────────────────────────────────────┐
│  Phase 2: Visual Grounding (Image-to-Code)                  │
│  • For visual pages: Generate standalone section images     │
│  • Perform deep visual extraction (tokens, spatial rhythm)  │
└──────────────────────────────┬──────────────────────────────┘
                               │
                               ▼
┌─────────────────────────────────────────────────────────────┐
│  Phase 3: Frontend Implementation & 3-Tier Anti-Slop        │
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

## 🛡️ Anti-Slop 3-Tier Filter & Craftsmanship Standards

### The Craftsmanship Criteria (C-1 to C-5)
* **C-1 Intentionality:** Every visual and copy decision has an articulable reason. If the only reason is "it's the AI default", the decision is a defect.
* **C-2 Functional Completeness:** Every interactive control works or does not exist. A button that cannot perform an action is a defect, not decoration.
* **C-3 Content-Driven Composition:** Every section exists because the product's narrative requires it, not because an AI template expects it.
* **C-4 Resilience:** The UI holds up across every state (empty, loading, error), every theme (light, dark), all breakpoints (mobile to desktop), and keyboard-only navigation.
* **C-5 Evidence Over Claims:** Everything presented as fact (numbers, uptime, testimonials, security badges) is real and verifiable, or omitted completely.

### The Keystone Logo-Swap Test (R-31)
> **"If the logo and product name were swapped out, would this design still feel unique and have its own character?"**  
> If the answer is **no**, the design is generic template slop and must be reworked before delivery.

---

## 🏛️ Repository Architecture

```text
.
├── SKILL.md                          # Root skill manifest for instant `npx skills add`
│
├── skills/
│   └── ui-design/
│       └── SKILL.md                  # Monorepo / sub-path skill entry
│
├── templates/
│   └── DESIGN.md                     # Universal DESIGN.md starter template for projects
│
├── references/
│   ├── anti-slop-rules.md            # Complete 38-rule catalog, C1-C5 standards, & dual-mode audit guide
│   ├── web-interface-guidelines.md   # Vercel a11y, form ergonomics, & performance rules
│   ├── image-to-code-workflow.md     # 3-phase image generation & visual extraction guide
│   ├── design-md-specification.md    # Specification for writing and reading DESIGN.md files
│   └── playwright-verification.md    # Autonomous browser auditing with @playwright/cli
│
├── README.md                         # Project documentation & quickstart
├── LICENSE                           # MIT License
└── .gitignore
```

---

## 🧪 Autonomous Playwright CLI Verification

Agents equipped with this skill can run automated browser audits on local dev servers:

```bash
# 1. Open persistent headless session
npx @playwright/cli open http://localhost:3000

# 2. Capture token-efficient DOM snapshot for accessibility review
npx @playwright/cli snapshot

# 3. Capture responsive screenshots across viewports
npx @playwright/cli screenshot --viewport-size 1440,900 --full-page --output .playwright/desktop.png
npx @playwright/cli screenshot --viewport-size 768,1024 --full-page --output .playwright/tablet.png
npx @playwright/cli screenshot --viewport-size 375,667 --full-page --output .playwright/mobile.png

# 4. Close session
npx @playwright/cli close
```

### Auto-Audit Checklist:
* [x] **DOM Snapshot:** Inspect interactive element map for unlabelled buttons (`aria-label`), missing form labels, and correct semantic tags.
* [x] **Desktop Visual Inspection:** Compare `.playwright/desktop.png` against the reference image or `DESIGN.md`.
* [x] **Mobile Overflow Check:** Verify `.playwright/mobile.png` has no clipped components or horizontal scrollbars (`scrollWidth === innerWidth`).
* [x] **Focus Ring Validation:** Test keyboard navigation to ensure visible focus rings (`focus-visible:ring-2`) appear on Tab navigation.

---

## 📋 Delivery Gate Checklist

Before declaring any design task complete, the agent verifies:

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

## 🤝 Contributing
Contributions are always welcome! Please see [CONTRIBUTING.md](CONTRIBUTING.md) for details on submitting anti-slop rules, design templates, and verification improvements.

---

## 📄 License
MIT © [Ravi Zikrillah](https://github.com/ravizikrillah)
