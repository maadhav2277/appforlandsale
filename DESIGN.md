# Design System Document: The Nocturnal Surveyor

## 1. Overview & Creative North Star
**Creative North Star: The Nocturnal Cartographer**

This design system is built for the "Nocturnal Surveyor"—an aesthetic that marries the precision of high-end surveying equipment with the quiet, atmospheric depth of a moonlit landscape. We are moving away from the "generic SaaS" look. Instead, we are leaning into a **High-End Editorial** experience. 

The goal is to make the user feel like they are operating a premium, specialized tool for land acquisition. We achieve this through:
*   **Intentional Asymmetry:** Breaking the 12-column grid to create a sense of discovery.
*   **Tonal Depth:** Replacing borders with sophisticated layer stacking.
*   **Luminous Accents:** Using our signature emerald palette to "illuminate" key data points against an obsidian void.

---

## 2. Colors
Our palette is a study in high-contrast elegance. We utilize deep obsidian tones for stability and luminous emerald for action.

### The "No-Line" Rule
To maintain a premium, bespoke feel, **1px solid borders are strictly prohibited for sectioning.** We do not use "boxes" to separate content. Boundaries must be defined through:
1.  **Background Color Shifts:** Placing a `surface_container_low` element against a `surface` background.
2.  **Strategic Spacing:** Using whitespace to imply containment.
3.  **Tonal Transitions:** Subtle shifts between obsidian shades.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers. We use the surface-container tiers to create depth:
*   **Background (`#02161d`):** The base level.
*   **Surface Container Lowest (`#001017`):** Used for "sunken" elements like search bars or secondary content.
*   **Surface Container High (`#192d34`):** Used for prominent interactive cards that need to "lift" toward the user.

### The "Glass & Gradient" Rule
Standard flat colors feel "out-of-the-box." To elevate the experience:
*   **Luminous CTAs:** Main buttons should use a gradient from `primary_fixed` (`#a1f4c8`) to `primary_fixed_dim` (`#85d7ad`) at a 135-degree angle.
*   **Surveyor Glass:** Floating navigation bars or modal overlays must use `surface_bright` with a 12px `backdrop-blur` and 60% opacity. This creates a "frosted lens" effect consistent with professional optical equipment.

---

## 3. Typography
We use **Manrope** exclusively. Its geometric yet approachable form fits the "Professional Surveyor" persona perfectly.

*   **Display & Headlines:** Use `display-lg` (3.5rem) for hero sections with intentional negative letter-spacing (-0.02em). These are our "Editorial Statements."
*   **The Power of Labels:** `label-md` and `label-sm` should be used for metadata (coordinates, acreage, price). These should often be in ALL CAPS with a slight tracking increase (+0.05em) to mimic the technical readout of a surveyor’s tool.
*   **Body Copy:** Use `body-lg` for descriptions. Ensure line heights are generous (1.6) to allow the deep background colors to "breathe" through the text.

---

## 4. Elevation & Depth
In this system, depth is a function of light and shadow, not lines.

### The Layering Principle
Depth is achieved by "stacking" the surface-container tiers. For instance:
1.  **Level 0:** `background`
2.  **Level 1:** `surface_container_low` (The Section)
3.  **Level 2:** `surface_container_highest` (The Card)

### Ambient Shadows
When an element must float (e.g., a property detail modal), use a "Nocturnal Shadow":
*   **Blur:** 40px to 60px.
*   **Opacity:** 15%.
*   **Color:** Use the `surface_container_lowest` (`#001017`) color rather than black. This ensures the shadow feels like a natural occlusion of light in an emerald-tinted environment.

### The "Ghost Border" Fallback
If a border is required for extreme accessibility or data-heavy grids, use a **Ghost Border**:
*   **Token:** `outline_variant` at 20% opacity. 
*   **Rule:** Never use a 100% opaque border.

---

## 5. Components

### Buttons
*   **Primary:** Rounded `full`. Background: `primary_container` (`#a1f4c8`). Text: `on_primary_container` (`#1a724f`). Add a subtle outer glow (4px blur) of the same color on hover.
*   **Secondary:** Rounded `full`. Background: `transparent`. Border: Ghost Border (`outline_variant` @ 30%). 

### Cards & Property Lists
*   **Rule:** No dividers. Use `surface_container_low` for the card body. 
*   **Interaction:** On hover, shift the card background to `surface_container_high` and apply a `primary_fixed` (emerald) left-accent bar (4px width).

### Input Fields
*   **Visual:** "Sunken" appearance. Use `surface_container_lowest`. 
*   **Focus State:** Do not just change the border color. Apply a subtle internal glow and change the label color to `primary_fixed`.

### Surveyor Chips
*   Used for land status (e.g., "Available", "Pending"). 
*   Use `secondary_container` with `on_secondary_container` text. Keep corners `md` (0.75rem) to differentiate from the `full` rounded buttons.

### Specialized Component: The Coordinate HUD
*   A custom floating element for land coordinates.
*   **Style:** `surface_bright` with `backdrop-blur`. Use `label-sm` in emerald for the data. This reinforces the "Nocturnal Surveyor" vibe.

---

## 6. Do’s and Don’ts

### Do:
*   **Do** use asymmetrical layouts. Place a high-contrast `display-lg` title overlapping a `surface_container_high` image block.
*   **Do** use emerald (`primary_fixed`) sparingly. It is a high-intensity signal; use it for calls to action and critical data points only.
*   **Do** leverage the `rounded-xl` (1.5rem) corner radius for large containers to soften the high-contrast professional vibe.

### Don’t:
*   **Don’t** use pure white (`#ffffff`) for body text. Use `on_surface_variant` (`#bec9c0`) to reduce eye strain in dark mode.
*   **Don’t** use standard 1px dividers to separate list items. Use 16px of vertical whitespace or a 1-step shift in surface color.
*   **Don’t** use vibrant "Error Red" indiscriminately. Use the `error_container` (`#93000a`) sparingly so it doesn't clash with the emerald palette.

---
**Director's Note:** This system is about the balance between the "void" (the dark background) and the "signal" (the emerald data). If a screen feels too busy, remove a container and let the typography do the work. If it feels too flat, add a layer of `surface_container_high`.