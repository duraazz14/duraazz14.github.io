# Design System Specification: The Editorial Portfolio

## 1. Overview & Creative North Star
**Creative North Star: "The Curated Gallery"**
This design system rejects the "template" look of the modern web in favor of high-end editorial layouts. It is built on the philosophy that a portfolio is not a database, but a curated exhibition. By leveraging intentional asymmetry, extreme typographic scale, and a "paper-on-glass" layering logic, we create an experience that feels both personally bespoke and hyper-polished.

The system moves away from rigid, boxy grids. Instead, it utilizes **tonal depth** and **active whitespace** to guide the eye. We don't use lines to separate ideas; we use distance and light.

---

## 2. Colors & Surface Logic
The palette is rooted in a "Crisp Neutral" foundation, punctuated by a high-energy Electric Blue (`primary`) and a sophisticated Emerald (`tertiary`).

### The "No-Line" Rule
**Prohibited:** 1px solid borders for sectioning or card containment. 
**The Standard:** Boundaries must be defined solely through background color shifts. For example, a `surface-container-low` section sitting on a `surface` background. If you feel the need to draw a line, increase your spacing by two increments on the scale instead.

### Surface Hierarchy & Nesting
Treat the UI as physical layers of fine stationery. 
*   **Base Layer:** `surface` (#fcf9f8) – The canvas.
*   **Secondary Content:** `surface-container-low` (#f6f3f2) – Used for subtle grouping.
*   **Interactive/Elevated Elements:** `surface-container-highest` (#e5e2e1) – Used for items that need to "pop" without using shadows.

### The "Glass & Gradient" Rule
To escape the "flat" feel of utility-first frameworks, use **Glassmorphism** for floating headers or navigation overlays. 
*   **Token:** `surface-container-lowest` at 80% opacity with a `20px` backdrop-blur.
*   **Signature Texture:** Use a subtle linear gradient on main CTAs: `primary` (#003ec7) to `primary-container` (#0052ff) at a 135-degree angle. This adds "soul" and a sense of light source to the interface.

---

## 3. Typography
We use a dual-sans-serif pairing to balance high-fashion editorial with technical precision.

*   **Display & Headlines (Manrope):** This is your "voice." Use `display-lg` (3.5rem) for hero statements with tight letter-spacing (-0.04em). The goal is impact and authority.
*   **Body & Labels (Inter):** This is your "clarity." Inter provides a neutral, highly readable counterpoint to the expressive Manrope.
*   **Intentional Asymmetry:** Avoid centering all text. Use "left-heavy" layouts where headlines sit at `10` or `12` on the spacing scale from the left margin, while body text is tucked into a narrower column to create a dynamic, editorial flow.

---

## 4. Elevation & Depth
In this system, "Elevation" is a measurement of light, not darkness.

### The Layering Principle
Achieve hierarchy by stacking tiers. Place a `surface-container-lowest` card (#ffffff) on a `surface-container-low` (#f6f3f2) section. This creates a soft, natural lift that feels premium and tactile.

### Ambient Shadows
Shadows are a last resort. When used (e.g., for a floating "Contact" button), they must be:
*   **Blur:** 32px – 64px.
*   **Opacity:** 4% – 6%.
*   **Color:** Use a tint of `on-surface` (#1c1b1b), never pure black. This mimics natural ambient light.

### The "Ghost Border" Fallback
If accessibility requires a container boundary (e.g., in high-contrast modes), use a **Ghost Border**:
*   **Token:** `outline-variant` (#c3c5d9) at **15% opacity**. It should be felt, not seen.

---

## 5. Components

### Buttons
*   **Primary:** Gradient of `primary` to `primary-container`. `full` roundedness. No shadow.
*   **Secondary:** `surface-container-highest` background with `on-surface` text.
*   **Tertiary/Ghost:** `on-background` text with a `primary` underline that expands on hover.

### Cards (The "Editorial Card")
*   **Styling:** No borders. Background: `surface-container-low`.
*   **Spacing:** Use `8` (2.75rem) internal padding to allow the content to breathe.
*   **Interaction:** On hover, shift background to `surface-container-high` and apply a `0.5rem` (lg) upward translation.

### Input Fields
*   **Styling:** Minimalist. Only a bottom border using `outline-variant` at 30% opacity. 
*   **Focus State:** The bottom border transitions to `primary` (#003ec7) with a width increase to 2px.

### Lists & Navigation
*   **Rule:** Forbid divider lines. Use vertical spacing (Scale `4` or `6`) to separate list items. 
*   **Navigation:** Use `label-md` for nav items, all-caps with 0.1em letter spacing for a "gallery" feel.

---

## 6. Do's and Don'ts

### Do
*   **Do** use extreme whitespace. If a section feels "finished," try adding one more level of spacing (e.g., move from `16` to `20`).
*   **Do** use `tertiary` (Emerald) for success states or "Available for Work" indicators to provide a sophisticated pop against the Charcoal/Blue.
*   **Do** use staggered entrance animations (200ms delay) for card grids to emphasize the "curated" feel.

### Don't
*   **Don't** use 100% black. Use `on-background` (#1c1b1b) for text to maintain a soft, high-end look.
*   **Don't** use standard "Drop Shadows" from a UI kit. They look cheap. Stick to tonal layering.
*   **Don't** center-align long blocks of text. It breaks the editorial "grid-less" illusion. Keep it left-aligned or use intentional offsets.
*   **Don't** use sharp corners. Use the `lg` (0.5rem) or `xl` (0.75rem) tokens to keep the aesthetic approachable and modern.