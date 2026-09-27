# Autonomous Playwright Verification & Testing Loop

This reference defines how AI coding agents leverage **`@playwright/cli`** (Microsoft's token-efficient browser automation CLI) to perform visual, functional, and accessibility verifications on frontend code.

---

## 1. Why Playwright CLI for Agents?

Unlike heavy browser automation suites that dump megabytes of HTML or full accessibility trees into LLM context, `@playwright/cli`:
* **Token Efficient:** Produces compact, indexed element snapshots (e.g. `[e1] <button "Deploy">`) designed specifically for AI agent reasoning.
* **Autonomous Feedback Loop:** Allows the agent to verify its own work in a real headless browser before handing off code to the human developer.
* **Multi-Viewport Visual Checks:** Captures deterministic screenshots at mobile (`375px`), tablet (`768px`), and desktop (`1440px`) to confirm layout stability and detect responsive breaks.

---

## 2. Installation & Quick Setup

To run locally in any Node.js project:

```bash
# Run directly without installation
npx @playwright/cli --help

# Or install as dev dependency
npm install -D @playwright/cli@latest
```

---

## 3. Core Commands for AI Agents

| Command | Action | Agent Purpose |
|---|---|---|
| `npx @playwright/cli open <url>` | Opens target URL in persistent browser session | Connects agent to local dev server (e.g. `http://localhost:3000`) |
| `npx @playwright/cli snapshot` | Outputs compact DOM & accessible element map | Inspects interactive elements, accessibility names, and form inputs |
| `npx @playwright/cli screenshot --output=<path>` | Saves viewport screenshot | Captures visual render for inspection |
| `npx @playwright/cli click <ref>` | Clicks targeted element (e.g., `e12`) | Tests dropdowns, modals, tabs, and CTA buttons |
| `npx @playwright/cli type <ref> <text>` | Types into input field | Tests form input validation and error states |
| `npx @playwright/cli close` | Closes active browser session | Cleans up headless process |

---

## 4. The Agent Autonomous Audit Protocol

Follow this 4-step loop after generating or refactoring UI components:

```
┌───────────────────────────────────────────────┐
│ 1. Boot Local Dev Server                      │
│    npm run dev &                              │
└───────────────────────┬───────────────────────┘
                        │
                        ▼
┌───────────────────────────────────────────────┐
│ 2. Snapshot & Accessibility Audit             │
│    npx @playwright/cli open http://localhost:3000
│    npx @playwright/cli snapshot               │
│    • Verify <button> and <a> usage            │
│    • Verify aria-labels on icon buttons       │
│    • Verify form input labels                 │
└───────────────────────┬───────────────────────┘
                        │
                        ▼
┌───────────────────────────────────────────────┐
│ 3. Multi-Viewport Visual Capture              │
│    • Desktop: 1440x900                        │
│    • Tablet:  768x1024                        │
│    • Mobile:  375x667                         │
│    • Inspect images with view_file / tools    │
└───────────────────────┬───────────────────────┘
                        │
                        ▼
┌───────────────────────────────────────────────┐
│ 4. Detect & Auto-Fix Discrepancies            │
│    • Horizontal overflow / horizontal scroll  │
│    • Button label wrapping                    │
│    • Visual alignment vs DESIGN.md            │
│    • Fix code immediately & re-verify         │
└───────────────────────────────────────────────┘
```

---

## 5. Automated Verification Script Template

Agents can run this inline bash routine to generate an instant visual audit bundle:

```bash
#!/usr/bin/env bash
set -e

OUT_DIR=".playwright-audit"
mkdir -p "$OUT_DIR"
URL="${1:-http://localhost:3000}"

echo "Starting Playwright audit on $URL..."

# 1. Open session
npx @playwright/cli open "$URL"

# 2. Capture DOM snapshot
npx @playwright/cli snapshot > "$OUT_DIR/snapshot.txt"

# 3. Capture Desktop (1440x900)
npx @playwright/cli screenshot --viewport-size 1440,900 --full-page --output "$OUT_DIR/desktop.png"

# 4. Capture Tablet (768x1024)
npx @playwright/cli screenshot --viewport-size 768,1024 --full-page --output "$OUT_DIR/tablet.png"

# 5. Capture Mobile (375x667)
npx @playwright/cli screenshot --viewport-size 375,667 --full-page --output "$OUT_DIR/mobile.png"

# 6. Close session
npx @playwright/cli close

echo "Audit complete. Artifacts saved to $OUT_DIR/"
```

---

## 6. What Agents Must Inspect in Snapshots & Screenshots

1. **Horizontal Scroll Check:** Inspect the mobile snapshot (`375px`). If elements have clipped widths or trigger horizontal scrollbars, immediately fix the layout with `overflow-x-hidden`, responsive padding, or `min-w-0`.
2. **Button Text Wrapping:** Review desktop screenshot (`1440px`). If any CTA text wrapped across multiple lines, either shorten the copy or expand the button padding.
3. **Hero Viewport Height:** Check that the entire hero message and CTAs are visible in the desktop screenshot without needing to scroll.
4. **Contrast Verification:** Ensure all text, buttons, and inputs are crisp and readable against background fills.
