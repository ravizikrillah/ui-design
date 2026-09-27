# Anti-Slop Visual Taste & Engineering Rules

This reference fuses **Leonxlnx/taste-skill** and **miqdadbadjuber/anti-slop** into a rigorous frontend craft standard. It holds every design decision to a strict purpose test, enforces the Craftsmanship Standard (C-1 through C-5), and categorizes rules into three operational tiers: **Hard Gate**, **Purpose-Gate**, and **Quality Locks**.

---

## 1. The Two Operational Modes

Before starting UI work, determine which mode applies:

* **Mode 1: DURING (Real-Time Enforcement):**
  Apply the rules actively during planning, styling, and coding. Prevents slop from entering the codebase from line one. Concludes with the Delivery Gate. Use for greenfield builds, feature additions, or proactive refactors.
* **Mode 2: AFTER (Post-Build / Audit):**
  Perform a formal audit of an existing project. Produce a numbered findings report (e.g. `anti-slop/audit-001-YYYY-MM-DD.md`).
  * **Findings Priority:**
    * **HIGH:** Any Hard Gate rule failure (R-02, R-03, R-17, R-18, R-23–R-28, R-32–R-38).
    * **MEDIUM:** Any Purpose-Gate failure without a written reason (R-01, R-04, R-06–R-10, R-12–R-14, R-19, R-22).
    * **LOW:** Quality Lock inconsistencies (R-05, R-11, R-15, R-16, R-20, R-21, R-29–R-31).
  * Require user approval for specific numbers before making edits, then fix and report.

---

## 2. The Craftsmanship Standard (C-1 to C-5)

"Not slop" is the floor, not the goal. A design passes only when it meets all five criteria:

* **C-1: Intentionality:** Every visual and copy decision has an articulable reason. If the only reason is "it's the AI default", the decision is a defect.
* **C-2: Functional Completeness:** Every interactive control works or does not exist. A button that cannot perform an action is a defect, not decoration.
* **C-3: Content-Driven Composition:** Every section exists because the product's narrative requires it, not because an AI template expects it.
* **C-4: Resilience:** The UI holds up across every state (empty, loading, error), every theme (light, dark), all breakpoints (mobile to desktop), and keyboard-only navigation.
* **C-5: Evidence Over Claims:** Everything presented as fact (numbers, uptime, testimonials, security badges) is real and verifiable, or omitted completely.

---

## 3. The Keystone Test

Before declaring any design task complete, answer this question:

> **"If the logo and product name were swapped out, would this design still feel unique and have its own character?"**

If the answer is **no**, the design is generic template slop. Rework it with distinct typography, layout variance, and content-driven rhythm.

---

## 4. The Three Dials Calibration

Every visual decision is gated by three numeric dials (`1-10` scale):

* **`DESIGN_VARIANCE`**
  * `1–3`: Rigid symmetry, classical enterprise grids, predictable rows.
  * `4–7`: Balanced asymmetric layout, split screens, offset white space.
  * `8–10`: Art-directed chaos, editorial overlapping, kinetic layout shifts.
* **`MOTION_INTENSITY`**
  * `1–3`: Static or strictly functional CSS transitions (`150ms`).
  * `4–7`: Subtle spring micro-interactions, scroll-driven staggered reveals.
  * `8–10`: Full cinematic choreography, GSAP scroll hijacks, sticky stacks, physics cursor tracking.
* **`VISUAL_DENSITY`**
  * `1–3`: Art gallery airy, generous whitespace, large breathing room.
  * `4–7`: Modern SaaS balance, clean cards, readable body content.
  * `8–10`: Bloomberg/Linear cockpit, compact data tables, monospaced metrics.

### Dial Presets
| Use Case | VARIANCE | MOTION | DENSITY |
|---|---|---|---|
| Modern SaaS Landing | 7 | 6 | 4 |
| Creative Studio / Agency | 9 | 8 | 3 |
| Premium Consumer (DTC) | 7 | 6 | 3 |
| Developer Portfolio | 6 | 5 | 4 |
| Designer Portfolio | 8 | 7 | 3 |
| Editorial / Publication | 6 | 4 | 3 |
| B2B Enterprise / Public Sector | 3 | 2 | 5 |

---

## 5. The 3-Tier Mandatory Rule Catalog

### Tier 1: Hard Gate (Absolute — No Exceptions)
Breaking any of these rules is a critical failure regardless of stated purpose:

* **R-02 (Copywriting):** FORBIDDEN: em dash character (`—`) in any text written by the agent. Use commas, periods, colons, or clean restructuring instead.
* **R-03 (Mobile Responsiveness):** Mobile layout must be flawless. Zero horizontal overflow (`overflow-x`), no colliding text, minimum 44px tap targets.
* **R-17 (Data & Numbers):** FORBIDDEN: fabricated statistics or metrics without real sources ("99.9% uptime", "10k+ users" with no evidence). Empty is better than deceptive.
* **R-18 (Testimonials):** FORBIDDEN: fictional testimonials, AI avatars, random names, invented job titles. If no real testimonials exist, omit the section.
* **R-23 (Clarification & Assets):** Before creating logos, profile avatars, or stats without explicit instructions, ask or use explicit placeholders (`[LOGO]`, `[REAL DATA]`). Never disguise placeholders as final.
* **R-24 (Navigation):** FORBIDDEN: navbar links to sections or pages that do not exist. Every nav link must lead to an accessible, real destination.
* **R-25 (Color Contrast):** All text must meet WCAG AA contrast (4.5:1 min for body, 3:1 for large 18px+ text). No light grey text on grey backgrounds; no white text over light gradient zones.
* **R-26 (Interactive Elements):** Every interactive control must have functional logic (modal opens/closes, menu toggles, real form submit feedback). Dead buttons/links are banned.
* **R-27 (UI States):** Every data-driven view must implement all three states: **Empty state**, **Loading state** (skeletal), and **Error state**.
* **R-28 (FAQ):** FORBIDDEN: generic template FAQs ("Can I cancel anytime?"). Every question must address real product user concerns.
* **R-32 (Keyboard Accessibility):** All controls must be operable via keyboard (`Tab`, `Shift+Tab`, `Enter`, `Space`, `Escape`). Visible focus rings (`focus-visible:ring-2`) are mandatory. Unreplaced `outline: none` is banned.
* **R-33 (No File/CSS Patching via Scripts):** FORBIDDEN: modifying UI or theming using regex/patch scripts on CSS files. Build features directly in component source code.
* **R-34 (Every Theme Shipped Must Work):** If a light/dark theme toggle is provided, both modes must be fully functional, contrast-compliant, and audited.
* **R-35 (Verify Before You Deliver):** Run/build the app before delivery. Click through interactive elements, verify them, and record evidence.
* **R-36 (No Fabricated Claims):** FORBIDDEN: fake compliance or security badges ("SOC 2", "ISO 27001", "300% faster") without verifiable proof.
* **R-37 (Design Direction Required):** Before building, load `DESIGN.md` or brand brief. If none exists and cannot be obtained, label output as *"draft without direction"* with dials ENERGY 1 / RHYTHM 1 / MOTION 1. Never silently fall back to sterile AI defaults.
* **R-38 (Real Content or Honest Placeholder):** All content must be real or clearly labeled (`[REAL DATA]`, "Coming soon").

---

### Tier 2: Purpose-Gate (Technique Allowed, Stated Purpose Required)
Techniques below are allowed, but they FAIL if used as a thoughtless default. The reason must serve brand identity or visual hierarchy:

* **R-01 (Color & Gradients):** AI-purple, blue-to-purple, or neon glow gradients are forbidden as defaults. Allowed only when part of an established brand identity with written justification.
* **R-04 (Icons):** Forbidden as default: generic AI icons (Sparkles, Magic Wand, Lightning, Star, Robot) and recognizable Lucide-style rounded thin-stroke sets used without thought. Icons must be genuinely relevant.
* **R-06 (Typography):** Forbidden as default: terminal monospace for headings or extreme uppercase tracking (`H O W   I T   W O R K S`). Fonts must match brand character.
* **R-07 (Backgrounds):** Blueprint lines, grid squares, and dot matrices are forbidden as generic defaults.
* **R-08 (Button Arrows):** Arrows (`→`, `↗`) must not be slapped onto every CTA. Use with proportion and purpose.
* **R-09 (Badges):** Generic capsule badges ("AI Powered", "Beta", "New") are forbidden without functional context.
* **R-10 (Glassmorphism Dose Cap):** Accent only (max 1–2 elements). FORBIDDEN on navbar, cards, modals, and sidebar simultaneously.
* **R-12 (Shadows):** Shadows must denote elevation hierarchy, not make every element float ambiguously.
* **R-13 (Glow Dose Cap):** Glow is permitted on at most 1–2 key focal points. Never on cards + buttons + icons + badges + borders at once.
* **R-14 (Feature Cards):** Feature cards must have visual variance reflecting content hierarchy, not 6 identical cloned boxes.
* **R-19 (Animations):** Animations must have clear UX purpose (hierarchy, state change, feedback). Never stack Fade-Up + Float + Scale + Bounce on every element.
* **R-22 (Illustrations):** Generic Undraw, Storyset, or 3D blob characters are forbidden. Use real screenshots or original art.

---

### Tier 3: Quality Locks (Consistency & Structural Discipline)

* **R-05 (Page Structure & Rhythm):** Banned repetitive AI templates (Hero + 3 cards + 3-step "How it works" + 3 pricing cards + 4-column footer). Page structure must follow content narrative.
* **R-11 (Border Radius Consistency):** Lock one border radius scale across the page. Banned: making every single element pill-shaped.
* **R-15 (Specific CTAs):** Replace generic labels ("Get Started", "Learn More", "Click Here") with contextual actions ("Start Free 14-Day Trial", "View Live Demo", "Download CLI").
* **R-16 (Copywriting Buzzwords):** BANNED AI words: "AI-Powered", "Next-Generation", "Revolutionary", "Seamless", "Cutting-Edge", "Intelligent", "Ultimate", "Elevate", "Unleash".
* **R-20 (Tone & Personality):** Maintain consistent copy register (don't mix technical jargon with informal slang).
* **R-21 (Whitespace):** Whitespace is a structural design element, not empty space to be filled.
* **R-29 (Content-Driven Sizing):** Section height and padding are determined by content density, not fixed template heights.
* **R-30 (Human Copy Audit):** Re-read every string for natural flow, eliminating passive-aggressive AI humility or fake craftsmanship.
* **R-31 (Keystone Check):** Logo-swap test must pass.

---

## 6. Official Design System Mapping

When the brief matches an existing standard, use official packages rather than hand-rolling CSS:

| If Brief Reads As... | Use Official Package | Rationale |
|---|---|---|
| Microsoft / Enterprise Dashboard | `@fluentui/react-components` | Official tokens, accessibility out of the box. |
| IBM / Heavy Data Analytics | `@carbon/react` + `@carbon/styles` | Mature data density and enterprise ergonomics. |
| Google / Android Ecosystem | `@material/web` + M3 tokens | Official Material 3 theming. |
| GitHub Devtool / Community | `@primer/react-brand` or `@primer/css` | Primer brand aesthetic. |
| Shopify App Surfaces | Polaris React (`@shopify/polaris`) | Required for Shopify admin fidelity. |
| Modern Accessible Foundation | `@radix-ui/themes` or `shadcn/ui` | Full primitive control, keyboard-accessible. |
| Modern Tailwind Web | Tailwind CSS v4 + native CSS variables | Clean utility-first execution without bloat. |

---

## 7. Motion Engineering Skeletons

### 7.1 Sticky-Stack Pattern (GSAP)
```tsx
"use client";
import { useRef, useEffect } from "react";
import { gsap } from "gsap";
import { ScrollTrigger } from "gsap/ScrollTrigger";
import { useReducedMotion } from "motion/react";

gsap.registerPlugin(ScrollTrigger);

export function StickyStack({ cards }: { cards: React.ReactNode[] }) {
  const containerRef = useRef<HTMLDivElement>(null);
  const shouldReduceMotion = useReducedMotion();

  useEffect(() => {
    if (shouldReduceMotion || !containerRef.current) return;

    const ctx = gsap.context(() => {
      const cardElements = gsap.utils.toArray<HTMLElement>(".stack-card");
      cardElements.forEach((card, i) => {
        if (i === cardElements.length - 1) return;

        ScrollTrigger.create({
          trigger: card,
          start: "top top",
          endTrigger: cardElements[cardElements.length - 1],
          end: "top top",
          pin: true,
          pinSpacing: false,
        });

        gsap.to(card, {
          scale: 0.94,
          opacity: 0.6,
          ease: "none",
          scrollTrigger: {
            trigger: cardElements[i + 1],
            start: "top bottom",
            end: "top top",
            scrub: true,
          },
        });
      });
    }, containerRef);

    return () => ctx.revert();
  }, [shouldReduceMotion]);

  return (
    <div ref={containerRef} className="relative">
      {cards.map((card, idx) => (
        <div
          key={idx}
          className="stack-card sticky top-0 min-h-[100dvh] flex items-center justify-center p-6"
        >
          {card}
        </div>
      ))}
    </div>
  );
}
```

### 7.2 Scroll-Reveal Stagger (Motion)
```tsx
"use client";
import { motion, useReducedMotion } from "motion/react";

export function RevealStagger({ items }: { items: React.ReactNode[] }) {
  const shouldReduce = useReducedMotion();

  return (
    <div className="grid grid-cols-1 md:grid-cols-3 gap-8">
      {items.map((item, idx) => (
        <motion.div
          key={idx}
          initial={shouldReduce ? false : { opacity: 0, y: 24 }}
          whileInView={{ opacity: 1, y: 0 }}
          viewport={{ once: true, amount: 0.2 }}
          transition={{
            duration: 0.5,
            delay: idx * 0.08,
            ease: [0.16, 1, 0.3, 1],
          }}
        >
          {item}
        </motion.div>
      ))}
    </div>
  );
}
```
