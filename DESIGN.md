```markdown
# Design System Document: The Topographic Editorial

## 1. Overview & Creative North Star: "The Digital Surveyor"
This design system moves away from the cluttered, transactional nature of traditional real estate platforms. Our Creative North Star is **"The Digital Surveyor."** We treat land not as a commodity, but as a destination. The aesthetic is rooted in high-end editorial layouts—think *Kinfolk* meets *National Geographic*. 

We achieve this through **Organic Asymmetry** and **Tonal Depth**. Instead of rigid grids and harsh borders, we use expansive white space and "layered landscapes" to guide the user. The experience should feel as stable as the ground itself, yet as fluid as a natural horizon.

---

## 2. Colors: The Earth & Atmosphere
Our palette is a sophisticated interplay of deep forest pigments and airy slate tones.

### The "No-Line" Rule
**Prohibition:** 1px solid borders are strictly forbidden for sectioning. 
**Execution:** Boundaries must be defined through background color shifts. A section using `surface-container-low` should sit directly against the `background` to create a soft, natural break. Use vertical white space to define "rooms" within the layout.

### Surface Hierarchy & Nesting
Treat the UI as physical layers of vellum.
- **Base:** `background` (#f3faff) for the vast majority of the canvas.
- **The Nested Stack:** Place a `surface-container-lowest` (#ffffff) card on top of a `surface-container-low` (#e6f6ff) section. This creates a "lifted" effect that feels intentional and premium.
- **Glassmorphism:** For floating map controls or navigation bars, use `surface` with a 70% opacity and a `24px` backdrop-blur. This allows the property imagery or map textures to bleed through, maintaining a sense of place.

### Signature Textures
- **The Horizon Gradient:** For Hero CTAs and primary buttons, use a subtle linear gradient from `primary` (#002d1c) to `primary_container` (#00452e) at a 135-degree angle. This adds "visual soul" and depth that flat hex codes lack.

---

## 3. Typography: Authority & Clarity
We utilize a dual-sans-serif approach to balance editorial character with functional precision.

- **The Voice (Manrope):** Our primary typeface for `display`, `headline`, and `title` scales. Manrope’s geometric yet warm proportions evoke modern stability.
    - *Editorial Note:* Use `display-lg` (3.5rem) with tighter letter-spacing (-0.02em) for property names to create an authoritative, "magazine cover" feel.
- **The Utility (Inter):** Reserved for `label-md` and `label-sm`. Inter provides maximum legibility for technical data like acreage, coordinates, and price-per-square-foot.
- **Hierarchy as Brand:** Use high contrast between `headline-lg` (2rem) in `primary` and `body-md` (0.875rem) in `on_surface_variant`. This ensures the brand "shouts" its confidence while the details "whisper" their data.

---

## 4. Elevation & Depth: Tonal Layering
Traditional drop shadows are too "digital." We prefer **Atmospheric Perspective.**

- **The Layering Principle:** Stack `surface-container` tiers. A sidebar should be `surface-container-high` (#ccedfe) against a `surface` map background. 
- **Ambient Shadows:** For floating elements like a property preview card on a map, use a custom shadow: `0px 20px 40px rgba(0, 31, 41, 0.06)`. Note the color—it’s a tinted version of `on-surface`, not pure black.
- **The Ghost Border:** If a boundary is required for accessibility in forms, use `outline-variant` (#c1c8c2) at **15% opacity**. It should be felt, not seen.

---

## 5. Components: Functional Elegance

### Property Cards
- **No Dividers:** Separate the image, title, and price using padding alone (referencing the `xl` 0.75rem roundedness for the container).
- **Background Shift:** Use `surface-container-lowest` for the card body to make it "pop" against the `surface-container-low` page background.

### Map Markers & Boundary Tools
- **The "Pin":** Use a `primary` (#002d1c) circular glyph with a thick `on_primary` border. When active, it should expand and glow with a `secondary_container` (#a1f4c8) halo.
- **Boundary Drawing:** Lines should be drawn using `secondary` (#116c4a) with a 2px width. The enclosed area should have a 10% opacity fill of `primary_fixed` (#b1f0ce) to simulate a "highlighted plot."

### Buttons
- **Primary:** Gradient fill (`primary` to `primary_container`), `on_primary` text, `xl` roundedness.
- **Secondary:** No fill. A `Ghost Border` (15% `outline`) and `on_secondary_container` text.
- **Tertiary:** Pure text-link style using `on_primary_fixed_variant` with a 2px underline that appears only on hover.

### Inputs & Search
- **The "Field-less" Search:** Use a `surface-container-highest` bar with no border. The "Search" icon should be `primary` to anchor the eye. 
- **Error States:** Use `error` (#ba1a1a) text but ground the input in `error_container` (#ffdad6) to soften the visual "alarm."

---

## 6. Do’s and Don’ts

### Do:
- **Do** use `surface-container` shifts to create sections.
- **Do** allow imagery to take up 60% of the screen in property details; the land is the hero.
- **Do** use `xl` (0.75rem) corners for large containers and `md` (0.375rem) for smaller interactive elements like chips.

### Don’t:
- **Don’t** use black (#000000) for text. Always use `on_surface` (#001f29) to keep the palette organic.
- **Don’t** use 1px solid borders to separate list items. Use 16px of vertical spacing instead.
- **Don’t** use harsh "Material Design" ripples. Use soft opacity fades (e.g., 100% to 80%) for hover states to maintain the premium feel.

---

## 7. Accessibility
- All text must maintain a 4.5:1 contrast ratio against its respective `surface` tier.
- Interactive targets (buttons, markers) must be at least 44x44px.
- Use `label-sm` (Inter) for fine print, but never go below `0.6875rem` to ensure legibility for older demographics often found in land investment.