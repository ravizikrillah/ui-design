# Image-to-Code Workflow: Image-First Website Design

This guide defines the 3-phase **Image-to-Code** methodology. When building visually demanding web projects (landing pages, portfolios, product launches), coding without visual reference produces generic AI slop. This workflow enforces visual creation before code implementation.

---

## 1. The Core Directive

```
[ Step 1: Generate Section Images ]
               │
               ▼
[ Step 2: Deep Visual Extraction ]
               │
               ▼
[ Step 3: Faithful Code Translation ]
```

1. **Image Generation First:** Create dedicated high-resolution visual reference images using whatever image-generation tool is available in your environment (`generate_image`, Imagen, DALL-E, Midjourney, etc.).
2. **Deep Visual Extraction Second:** Systematically inspect the generated images to extract color palettes, typography scale, spatial rhythm, and component states.
3. **Frontend Implementation Third:** Write semantic, accessible code that directly mirrors the extracted visual truth.

---

## 2. Section Generation Rules

### 2.1 The "One Image Per Section" Rule
* **Rule:** Generate dedicated standalone horizontal images (`16:9` or `3:2`) for each major section.
* **Why:** Collapsing 8 sections into one single full-page board renders copy illegible, spacing blurry, and button details unextractable.
* **Section Allocation:**
  * Section 1: Hero & Primary Navigation → Image 1
  * Section 2: Social Proof / Trusted By / Metrics → Image 2
  * Section 3: Feature Bento Grid → Image 3
  * Section 4: Interactive Product Showcase / Deep Dive → Image 4
  * Section 5: Customer Testimonial / Editorial Quote → Image 5
  * Section 6: Final CTA & Footer → Image 6

### 2.2 Do Not Crop Old Images
* Never crop, cut out, or digitally zoom into a section from an older full-page board.
* Cropping destroys:
  * Native type scale relationships.
  * Precise border radiuses and hairline strokes.
  * Spatial margins and paddings.
* **Always generate a fresh standalone image** preserving the same design system tokens and visual world.

---

## 3. High-Conversion Image Generation Prompts

When generating section images with an image tool, use structured prompt architecture:

### 3.1 Hero Section Prompt Formula
```
Modern website hero section UI for [Brand / Product], [Aesthetic Vibe: e.g. Minimalist Swiss Dark Tech].
Left: Bold display typography "[Headline Text]" in clean grotesque sans-serif, concise subtext, one crisp high-contrast button "[CTA Label]".
Right: High-fidelity interactive UI panel showing [Key product visual / 3D artifact / clean data architecture].
Atmosphere: Deep zinc background (#09090b), single electric cobalt accent, subtle diffused atmospheric glow, zero clutter, immaculate spatial hierarchy. Clean web screenshot, high resolution, desktop viewport.
```

### 3.2 Bento Grid Prompt Formula
```
Modern website feature bento grid UI section for [Product], clean modular layout with 4 asymmetric tiles.
Tile 1: Large horizontal tile with interactive live preview and visual chart.
Tile 2: Square card with high-contrast icon and single stat metric.
Tile 3: Deep emerald tinted card highlighting security and enterprise compliance.
Tile 4: Wide card with live activity stream.
Atmosphere: Subtle 1px borders (rgba(255,255,255,0.08)), rounded corners (16px), dark theme, airy spacing, crisp legible labels.
```

---

## 4. Deep Visual Extraction Matrix

Before writing any code, execute this extraction analysis:

```markdown
### Visual Extraction Sheet: [Section Name]
* **Canvas Background:** Exact hex (e.g., `#09090b`) or gradient stops.
* **Surface Containers:** Card fills (e.g., `rgba(255, 255, 255, 0.03)` with `border-white/10`).
* **Accent Token:** Single focal color (e.g., `#3b82f6` or `#10b981`).
* **Display Typography:**
  * Headline: tracking, line height ratio, casing, approximate scale (`text-5xl md:text-6xl`).
  * Body: color tone (`text-zinc-400`), max reading width (`max-w-xl`).
* **Component Anatomy:**
  * Primary Button: padding (`px-6 py-3`), radius (`rounded-full` vs `rounded-lg`), shadow depth.
  * Card Radii: uniform scale (e.g., `rounded-2xl`).
* **Layout Geometry:**
  * Split proportions: 50/50, 60/40, or 3-column asymmetric.
  * Section padding: generous vertical rhythm (`py-24 md:py-32`).
```

---

## 5. Fallback When Image Generation Is Unavailable

If no image generation tool is accessible:
1. **Never build fake div-based screenshot slop** (nested rectangles mimicking app dashboards).
2. Reach for real photography via `https://picsum.photos/seed/{descriptive-seed}/{w}/{h}` or curated Unsplash URLs.
3. For brand logos, use real SVG marks via Simple Icons (`https://cdn.simpleicons.org/{slug}/ffffff`).
4. Keep the interface typographic, clean, and restrained rather than filling space with fake UI chrome.
