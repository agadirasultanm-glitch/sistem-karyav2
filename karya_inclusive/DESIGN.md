# Design System Document: Empowered Clarity

## 1. Overview & Creative North Star: "The Human Compass"
This design system moves away from the clinical, "utility-first" look of traditional job portals. Instead, it adopts the **Human Compass**—a creative North Star that treats accessibility not as a constraint, but as a premium aesthetic. 

The experience is defined by **Editorial Accessibility**: bold, unapologetic typography, generous negative space, and a high-contrast palette that feels sophisticated rather than harsh. We break the "template" look through intentional asymmetry—placing content in off-center blocks that guide the eye—and layering surfaces like sheets of fine stationery. This is a space of dignity, power, and professional warmth.

---

## 2. Colors: Tonal Depth & High Contrast
Our palette centers on the authoritative `primary` (#001855) and the energetic `secondary` (#7c5800). These provide the necessary WCAG AAA contrast while maintaining a professional, high-end feel.

### The "No-Line" Rule
To achieve a signature, modern look, **1px solid borders are strictly prohibited for sectioning.** Boundaries must be defined solely through background color shifts. 
- Use `surface` (#fcf9f8) for the main canvas.
- Use `surface-container-low` (#f6f3f2) to define secondary content areas.
- Use `surface-container-high` (#eae7e7) for interactive elements like cards.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers. A `surface-container-lowest` card should sit atop a `surface-container-low` section to create a soft, natural lift. This nesting provides visual structure without the "clutter" of lines.

### The "Glass & Gradient" Rule
For floating elements (modals, navigation bars), use **Glassmorphism**. Apply the `surface` color at 80% opacity with a `24px` backdrop blur. 
- **Signature Texture:** For primary CTAs and Hero sections, use a subtle linear gradient from `primary` (#001855) to `primary_container` (#002a84) at a 135-degree angle. This adds "soul" and depth to the deep blues.

---

## 3. Typography: The Lexend Scale
We use **Lexend** across the entire system. Designed specifically to reduce visual stress and improve reading proficiency, Lexend is the perfect marriage of high-end design and inclusive functionality.

- **Display (lg/md/sm):** Used for "Hero" moments. Use `display-lg` (3.5rem) for impact. These should be set with tighter letter-spacing (-0.02em) to feel like a high-fashion masthead.
- **Headline (lg/md/sm):** Reserved for section starts. Headlines should use `on_surface` (#1b1c1c) to maintain a crisp, authoritative voice.
- **Body (lg/md):** The workhorse. Body-lg (1rem) is our default for job descriptions to ensure maximum legibility for users with visual impairments.
- **Labels:** Use `label-md` in all-caps with increased letter-spacing (0.05em) for category tags to provide a sophisticated, metadata-rich look.

---

## 4. Elevation & Depth: Tonal Layering
In this system, depth is a feeling, not a shadow. 

- **The Layering Principle:** Stack `surface-container` tokens to create hierarchy. A profile dashboard might use `surface` as the base, `surface-container-low` for the sidebar, and `surface-container-highest` for the active workspace.
- **Ambient Shadows:** When a component must "float" (like a FAB or a Tooltip), use an extra-diffused shadow: `box-shadow: 0 12px 40px rgba(0, 22, 79, 0.08);`. Note the use of a tinted shadow (using the `on_primary_fixed` hue) rather than grey.
- **The "Ghost Border" Fallback:** If a boundary is required for accessibility in high-glare environments, use the `outline_variant` token at **15% opacity**. It should be felt, not seen.
- **Interactive Focus:** Focus states are non-negotiable. Use a 3px solid ring of `secondary_container` (#feb700) with a 2px offset to ensure the active element is unmistakable.

---

## 5. Components

### Buttons
- **Primary:** Gradient fill (`primary` to `primary_container`), `on_primary` text, `xl` (1.5rem) roundedness. Padding: `16px 32px`.
- **Secondary:** `secondary_fixed` (#ffdea8) background with `on_secondary_fixed` (#271900) text. This provides a warm, inviting alternative to the heavy primary button.
- **Interaction:** On hover, buttons should scale slightly (1.02x) and deepen their shadow—giving tactile feedback to the user.

### Input Fields
- **Styling:** Forgo the traditional box. Use a `surface-container-highest` fill with a bold `title-sm` label sitting above it. 
- **States:** On focus, the background shifts to `surface_lowest` and an `outline` (#737780) appears at the bottom (2px) only, mimicking an elegant underlined form.

### Cards & Lists
- **The Forbiddance:** No divider lines between list items.
- **The Solution:** Use `24px` of vertical whitespace (the "Breath") or alternating subtle background shifts (`surface-container-low` vs `surface-container-lowest`).
- **Cards:** Use `lg` (1rem) rounding. A card should feel like a solid object. Use `title-lg` for job titles to ensure they are the first thing a screen reader or a scanning eye hits.

### Selection Chips
- Use `full` (9999px) rounding.
- **Unselected:** `surface-container-high` background.
- **Selected:** `primary` background with `on_primary` text. This high-contrast jump clearly signals a "state change" to the user.

---

## 6. Do's and Don'ts

### Do
- **Do** use massive touch targets. Every interactive element must have a minimum hit area of `48x48dp`.
- **Do** use `primary_fixed` (#dce1ff) for "Empowerment" banners—it’s soft on the eyes but holds professional weight.
- **Do** leverage ARIA labels for every decorative gradient or icon to ensure screen readers focus on content.
- **Do** lean into white space. If a layout feels "crowded," double the spacing scale.

### Don't
- **Don't** use pure black (#000000) for text. Use `on_surface` (#1b1c1c) to keep the "Editorial Warmth."
- **Don't** use standard 1px grey dividers. They create visual "noise" that distracts users with cognitive disabilities.
- **Don't** rely on color alone to convey meaning (e.g., an error shouldn't just be red; it must have a `headline-sm` prefix like "Error:").
- **Don't** use small, "dainty" icons. Icons should be `24px` or `32px` to match the bold Lexend typography.