# Vercel Web Interface Guidelines Compliance

This guide details the engineering, usability, and accessibility rules adapted from Vercel's Web Interface Guidelines. Every frontend component built by the agent must comply with these standards.

---

## 1. Accessibility (a11y)

* **Semantic HTML First:** Use `<button>`, `<a>`, `<label>`, `<nav>`, `<main>`, `<header>`, `<footer>` instead of generic `<div>` tags with click handlers.
* **Icon Buttons:** Any icon-only button must have an explicit `aria-label`:
  ```tsx
  <button aria-label="Close dialog" onClick={onClose}>
    <XIcon aria-hidden="true" className="w-5 h-5" />
  </button>
  ```
* **Decorative Icons:** Decorative SVG icons must carry `aria-hidden="true"`.
* **Async Feedback:** Dynamically appearing toasts, alerts, and inline form errors must include `aria-live="polite"`.
* **Heading Hierarchy:** One `<h1>` per page. Headings must follow logical nesting (`<h2>` -> `<h3>`). Anchor links on headings should have `scroll-margin-top: 5rem` to prevent sticking behind fixed headers.
* **WCAG AA/AAA Contrast:**
  * Normal text (< 18px): minimum **4.5:1** contrast ratio against background.
  * Large text (≥ 18px bold or ≥ 24px regular): minimum **3:1** contrast ratio.
  * Interactive borders/icons: minimum **3:1** contrast ratio.
* **Skip Links:** Include a hidden skip link for keyboard users:
  ```tsx
  <a href="#main-content" className="sr-only focus:not-sr-only focus:fixed focus:top-4 focus:left-4 z-50 bg-black text-white px-4 py-2 rounded">
    Skip to content
  </a>
  ```

---

## 2. Focus States & Keyboard Navigation

* **Visible Focus:** Interactive elements must have clear, high-contrast focus rings:
  ```css
  focus-visible:outline-none focus-visible:ring-2 focus-visible:ring-offset-2 focus-visible:ring-blue-600
  ```
* **Ban on Unreplaced Outline-None:** Never write `outline-none` without an immediate `focus-visible:ring-*` replacement.
* **Focus-Visible over Focus:** Use `:focus-visible` so mouse clicks do not display rings, while keyboard navigation (Tab) does.
* **Compound Groups:** Use `:focus-within` on input groups with trailing icons or buttons to focus the entire wrapper.
* **Header/Footer Clearance:** Sticky headers and overlays must never obscure focused inputs or buttons during keyboard tabbing.

---

## 3. Form Design & Usability

* **Labels Above Inputs:** Position labels above inputs, not as placeholders. Placeholders disappear upon typing and harm cognitive retention.
* **Clickable Targets:** Associate labels using `htmlFor="input-id"` or wrap the input inside the `<label>`.
* **Non-Blocking Paste:** Never intercept or disable paste (`onPaste={(e) => e.preventDefault()}` is strictly banned). Users must be able to paste credentials, tokens, and verification codes.
* **Input Mode & Type:**
  * Email: `type="email" autoComplete="email"`
  * Phone: `type="tel" autoComplete="tel"`
  * One-Time Passcodes: `inputMode="numeric" autoComplete="one-time-code"`
* **Spellcheck Off:** Set `spellCheck={false}` on code inputs, emails, usernames, and hex colors.
* **Inline Errors:** Render error messages directly beneath the offending input. Focus the first invalid field upon form submission.
* **Submit Button State:** Keep submit buttons enabled until network requests initiate. Show an inline spinner while disabling the button during in-flight requests.

---

## 4. Typography & Copy Engineering

* **Widow Prevention:** Apply `text-wrap: balance` on section headings and `text-pretty` on body copy.
* **Numeric Columns:** Use `font-variant-numeric: tabular-nums` (Tailwind `tabular-nums`) for currency, timers, and data tables to prevent layout shifting.
* **Typographic Punctuation:**
  * Use real curly quotes `“` and `”` instead of straight ASCII quotes `"`.
  * Use proper ellipsis `…` (`&hellip;`) instead of three periods `...`.
  * Use non-breaking spaces `&nbsp;` between values and units (e.g., `10&nbsp;MB`, `⌘&nbsp;K`).
* **Microcopy Rules:**
  * Active voice: "Generate API Token" instead of "API Token will be generated".
  * Specific labels: "Save Project" instead of generic "Submit" or "Continue".
  * Loading state copy ends with ellipsis: "Deploying…", "Saving changes…".

---

## 5. Layout Stability & Performance (Core Web Vitals)

* **Zero Cumulative Layout Shift (CLS):** Always provide explicit `width` and `height` (or aspect-ratio containers) on `<img>` and `<video>` tags.
* **Above-the-Fold Media:** Add `priority` (Next.js) or `fetchpriority="high"` to hero visuals.
* **Below-the-Fold Media:** Set `loading="lazy"` on non-critical images.
* **Layout Thrashing Prevention:** Never read DOM geometry (`getBoundingClientRect`, `offsetHeight`) inside render cycles or animation frames without batching.
* **Flex Truncation:** Any flex child containing truncated text must declare `min-w-0` to allow ellipsis truncation without blowing out parent widths.

---

## 6. Mobile & Touch Ergonomics

* **Minimum Hit Target:** All interactive controls (buttons, links, switches) must measure at least `44px × 44px`.
* **Touch Action:** Set `touch-action: manipulation` on buttons to eliminate the 300ms double-tap zoom delay on mobile browsers.
* **Overscroll Containment:** Set `overscroll-behavior: contain` on slide-out drawers, modal dialogs, and mobile navigation menus to prevent background page scroll chaining.
* **Safe Area Insets:** For full-bleed mobile views, incorporate `env(safe-area-inset-top)` and `env(safe-area-inset-bottom)`.

---

## 7. Dark Mode & Hydration Safety

* **Dark Mode Meta:** Set `color-scheme: dark` on the root `<html>` element when dark mode is enabled to ensure native inputs, select dropdowns, and scrollbars render correctly.
* **Theme Color Meta:** Maintain `<meta name="theme-color" content="...">` matching the active page background.
* **Hydration Protection:**
  * Date/time formatting rendered on client components must avoid hydration mismatch between server timezones and client timezones.
  * Inputs with a `value` prop must provide an `onChange` handler. For uncontrolled components, use `defaultValue`.
