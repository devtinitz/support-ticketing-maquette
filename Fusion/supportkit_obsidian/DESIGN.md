# Design System: The Kinetic Archive

## 1. Overview & Creative North Star
**Creative North Star: "The Kinetic Archive"**
This design system moves away from the static, boxy nature of traditional SaaS dashboards toward a "Kinetic Archive"—a space that feels fluid, high-velocity, and precision-engineered. Inspired by the editorial clarity of Vercel and the functional density of Linear, this system prioritizes content over containers.

To break the "template" look, we utilize **Intentional Asymmetry**. Dashboards should not be perfectly mirrored; use varying column widths and "floating" utility panels to create a rhythmic, editorial flow. We replace rigid structural lines with tonal depth, creating a UI that feels grown rather than built.

---

## 2. Colors: Tonal Atmosphere
The palette is rooted in deep obsidian tones, utilizing the Material Design 3 token logic to create a sophisticated, multi-layered environment.

### The "No-Line" Rule
**Explicit Instruction:** Prohibit the use of 1px solid borders for sectioning. 
Boundaries must be defined through background shifts. A `surface-container-low` widget sitting on a `surface` background provides all the separation required. If the eye cannot distinguish the change, increase the tonal contrast of the background, do not add a line.

### Surface Hierarchy & Nesting
Treat the UI as a series of physical layers:
*   **Base (`surface` / `#0b1326`):** The canvas.
*   **Navigation (`surface-container` / `#171f33`):** The primary sidebar/anchor.
*   **Content Cards (`surface-container-high` / `#222a3d`):** Elevated data points.
*   **Active Modals (`surface-container-highest` / `#2d3449`):** The peak of the visual stack.

### The "Glass & Gradient" Rule
For primary actions and high-level summaries (e.g., *Tableau de bord* metrics), use **Glassmorphism**. Apply `surface-bright` at 60% opacity with a `backdrop-filter: blur(12px)`. 
*   **Signature Textures:** Use a subtle linear gradient on primary CTAs: `primary` (#c0c1ff) to `primary-container` (#8083ff) at 135 degrees. This adds "soul" and a metallic sheen that flat hex codes lack.

---

## 3. Typography: Editorial Authority
We pair **Inter** (Headings) for its technical precision with **Satoshi** (Body) for its humanist, modern character.

*   **Display & Headline (Inter):** High tracking (-0.02em) and tight leading. Used for "Le Chiffre d'Affaires" or "Statistiques Globales." It conveys authority.
*   **Body & Labels (Satoshi):** Increased line height (1.6) to ensure French compound words have room to breathe.
*   **Hierarchy as Identity:** Use `display-md` for empty states to make them feel like a magazine spread rather than an error.

---

## 4. Elevation & Depth
Depth is a functional tool, not a decoration.

*   **The Layering Principle:** Stack `surface-container-lowest` cards on a `surface-container-low` section. This "recessed" look creates a natural focus area for data entry.
*   **Ambient Shadows:** For floating elements like *Menus contextuels*, use a 32px blur, 0% spread, and 6% opacity. The shadow color must be a tinted version of `on-surface` (a deep indigo-blue) to simulate natural light refraction.
*   **The "Ghost Border" Fallback:** If accessibility requires a border, use the `outline-variant` token at **15% opacity**. It should be felt, not seen.

---

## 5. Components: Precision Primitives

### Buttons & Interactive
*   **Primary:** Indigo gradient (`primary` to `primary-container`). Rounded-md (12px). Text: "Confirmer la sélection."
*   **Secondary:** Ghost style. No background, `on-surface` text. On hover, a subtle `surface-container-high` fill emerges.

### Input Fields & Search
*   **Style:** No background fill by default; only a `surface-container-highest` bottom-heavy shadow. 
*   **Focus State:** The `primary` color glows softly as an inner-shadow, rather than a thick outer ring.
*   **Labels:** Use `label-sm` in all-caps with 0.05em letter spacing for a "Pro" hardware-interface look.

### Cards & Lists
*   **The Divider Ban:** Strictly forbid `<hr>` tags or border-bottoms. Use **24px vertical white space** or a subtle shift from `surface` to `surface-container-low` to separate ticket items in the "File d'attente."
*   **Chips:** Use `secondary-container` with `on-secondary-container` text for "Résolu" or "En cours" status. Keep corners `full` (pill-shaped) to contrast with the 12px card corners.

### Contextual Components (The "SupportKit" Specials)
*   **The Command Palette:** A centered, floating glass container (`surface-container-highest` at 80% opacity) for quick navigation (*Rechercher un ticket...*).
*   **The Timeline:** A vertical thread for support history using `outline-variant` as a 2px track, but only visible on hover.

---

## 6. Do's and Don'ts

### Do
*   **Use French Layout Logic:** French text is 15-20% longer than English. Ensure your containers (`surface-container`) use flexible widths or `min-width` to prevent truncation of "Paramètres de l'organisation."
*   **Embrace Negative Space:** If a section feels "empty," leave it. Do not fill it with decorative lines.
*   **Use Subtle Micro-interactions:** Buttons should scale down by 2% (0.98) on click to simulate physical resistance.

### Don't
*   **Don't use pure black (#000):** Use `surface-container-lowest` (#060e20) for the deepest blacks to maintain the "Indigo" atmosphere.
*   **Don't use high-contrast borders:** They shatter the "glass" illusion and make the UI look dated.
*   **Don't crowd the Sidebar:** Use `title-sm` for sidebar categories and leave at least 32px of padding between the icons and the edge of the screen.

---
*Document end. Direct all inquiries to the Design Director regarding token deviations.*