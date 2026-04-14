# Design System Document: Precision Clinical Editorial

## 1. Overview & Creative North Star
**Creative North Star: The Clinical Curator**

This design system moves beyond the generic "medical portal" aesthetic to embrace a **High-End Editorial** experience. We are not just displaying data; we are curating clinical excellence. The system balances the cold precision of medical technology with the warmth of human-centric care. 

To break the "template" look, we employ **Intentional Asymmetry**. Large-scale typography (Manrope) provides an authoritative, editorial voice, while breathable white space and overlapping "glass" layers create a sense of advanced, multi-dimensional technology. The layout should feel like a premium medical journal brought to life—structured and trustworthy, yet fluid and modern.

---

## 2. Colors: Tonal Depth & The "No-Line" Rule
Our palette is anchored by the deep, authoritative `primary` (#005143) and its lighter, more approachable `primary_container` (#036b59).

### The "No-Line" Rule
**Explicit Instruction:** Traditional 1px solid borders are strictly prohibited for sectioning. Structural boundaries must be defined through:
1.  **Background Shifts:** Transitioning from `surface` (#f8f9fa) to `surface_container_low` (#f3f4f5).
2.  **Tonal Transitions:** Using subtle shifts in the neutral scale to define content blocks.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers—stacked sheets of frosted glass. 
- **Base Layer:** `surface` (#f8f9fa).
- **Secondary Sectioning:** `surface_container_low` (#f3f4f5).
- **Elevated Cards/Modules:** `surface_container_lowest` (#ffffff). This creates a "natural lift" without the clutter of lines.

### The "Glass & Gradient" Rule
To evoke a high-tech clinical feel, use **Glassmorphism** for floating navigation bars or overlay modals. 
- **Recipe:** Use `surface` at 80% opacity + `backdrop-filter: blur(12px)`.
- **Signature Textures:** Apply a linear gradient from `primary` (#005143) to `primary_container` (#036b59) on hero sections and main CTAs. This adds "visual soul" and depth that a flat fill cannot provide.

---

## 3. Typography: The Editorial Voice
We utilize a dual-font system to balance clinical precision with modern technology.

*   **Display & Headlines (Manrope):** Chosen for its geometric clarity and modern "tech" feel. Use `display-lg` (3.5rem) with tight letter-spacing (-0.02em) for hero headers to command attention.
*   **Body & Labels (Inter):** Chosen for its exceptional legibility in data-heavy contexts.

**Hierarchy as Identity:**
- **Authority:** Use `headline-lg` (2rem) in `on_surface` for section titles.
- **Precision:** Use `label-md` (0.75rem) in `tertiary` (#0035bf) for small, all-caps metadata or "Micro-copy" to evoke a scientific, lab-ready feel.

---

## 4. Elevation & Depth: Tonal Layering
We reject the heavy, "muddy" shadows of the past. 

### The Layering Principle
Depth is achieved by stacking surface tokens. For example, a "Summary Card" should be `surface_container_lowest` (#ffffff) placed on a background of `surface_container` (#edeeef). This provides a crisp, clean separation.

### Ambient Shadows
When a component must "float" (e.g., a critical diagnostic popover):
- **Blur:** 32px to 64px.
- **Opacity:** 4% to 6%.
- **Color:** Use a tinted version of `on_surface` (#191c1d) rather than pure black to keep the clinical environment feeling light and sterile.

### The "Ghost Border" Fallback
If a border is required for accessibility (e.g., input fields), use the **Ghost Border**: `outline_variant` (#bec9c4) at **20% opacity**. Never use 100% opaque borders.

---

## 5. Components: Clinical Primitives

### Buttons
- **Primary:** Gradient fill (`primary` to `primary_container`), `on_primary` text, `roundness-md` (0.75rem).
- **Secondary:** `surface_container_high` fill with `primary` text. No border.
- **Tertiary:** Ghost style; `primary` text with an underline that appears only on hover.

### Medical Data Cards
- **Construction:** Use `surface_container_lowest` (#ffffff). 
- **Rule:** Forbid divider lines. Use `spacing-lg` (vertical white space) to separate patient data from diagnostic results.
- **Radius:** `xl` (1.5rem) to soften the "clinical" edge and make the tech feel accessible.

### Input Fields
- **Background:** `surface_container_low` (#f3f4f5).
- **Active State:** A 2px "Ghost Border" using `tertiary` (#0035bf) at 40% opacity.
- **Rounding:** `sm` (0.25rem) to maintain a sense of structured data entry.

### Clinical Status Chips
- **Success:** `primary_fixed` (#9ff2db) background with `on_primary_fixed_variant` text.
- **Warning/Error:** `error_container` (#ffdad6) background with `on_error_container` text.

---

## 6. Do's and Don'ts

### Do:
- **Do** use `tertiary` (#0035bf) sparingly as a "Trust Accent" for links, progress bars, and critical data points.
- **Do** leverage the `roundness-full` (9999px) token for search bars and tags to contrast against the grid-based data modules.
- **Do** use asymmetrical margins (e.g., a wider left margin for body text) to create an editorial, "white-paper" layout.

### Don't:
- **Don't** use 100% black text. Use `on_surface` (#191c1d) to maintain a premium, softer contrast.
- **Don't** use "Drop Shadows" on standard cards. Rely on tonal background shifts.
- **Don't** crowd the interface. If a section feels "busy," increase the vertical padding using the `xl` spacing scale rather than adding dividers.