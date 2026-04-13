# Design System Specification

## 1. Overview & Creative North Star: "The Digital Concierge"

This design system is built upon the philosophy of **The Digital Concierge**. We move away from the "software-as-a-tool" aesthetic toward "software-as-a-service." The experience must feel curated, effortless, and premium. 

To achieve this, we reject the rigid, "boxed-in" layout of traditional helpdesk widgets. Instead, we utilize **Soft Minimalism**—a strategy that prioritizes breathing room, intentional asymmetry, and tonal depth over structural lines. By leveraging the Inter typeface across a wide dynamic range, we create an editorial hierarchy that guides the user’s eye through white space rather than borders. The goal is a widget that feels less like a popup and more like a high-end physical stationery set unfolding on the screen.

---

## 2. Colors: Tonal Depth & Soul

We utilize a sophisticated palette where the "Blue-Violet" provides the authoritative voice and the "Emerald" provides the reassurance.

### The Palette
*   **Primary (Action):** `#4648d4` (Blue-Violet) – Used for high-emphasis actions.
*   **Primary Container:** `#6063ee` – Used for subtle backgrounds and gradient starts.
*   **Tertiary (Success):** `#006c49` – Used for positive status and resolution.
*   **Surface:** `#f7f9fb` – The standard background canvas.
*   **Surface Container (Lowest to Highest):** `#ffffff` to `#e0e3e5` – The engine of our hierarchy.

### The "No-Line" Rule
**Explicit Instruction:** Designers are prohibited from using 1px solid borders for sectioning or grouping. Layout boundaries must be defined solely through background color shifts. For example, a chat input area should sit on `surface-container-low` against a `surface` background. Lines feel like barriers; color shifts feel like transitions.

### The "Glass & Gradient" Rule
To ensure the widget feels "alive," major touchpoints (like the FAB or Header) should utilize a signature gradient: `primary` (#4648d4) to `primary-container` (#6063ee) at a 135-degree angle. Floating panels should employ **Glassmorphism**: use `surface-container-lowest` at 85% opacity with a 12px backdrop-blur to allow the host website's personality to bleed through the edges.

---

## 3. Typography: Editorial Authority

We use **Inter** exclusively. By varying weight and optical sizing, we create a sophisticated narrative flow.

*   **Display-Sm (2.25rem / Bold):** Used for "Hello" or welcome states. High impact, low frequency.
*   **Title-Md (1.125rem / Medium):** The standard for panel headers. It provides a grounded, professional anchor.
*   **Body-Md (0.875rem / Regular):** The workhorse for chat bubbles and descriptions. Set to `on-surface-variant` for secondary info.
*   **Label-Sm (0.6875rem / Semi-Bold):** Used for all-caps "Overline" text or tiny metadata. Increases the "premium" feel.

The hierarchy is built on **Contrast**: Large headlines paired with significantly smaller, well-spaced body text creates a sense of luxury and intentionality.

---

## 4. Elevation & Depth: Tonal Layering

We convey hierarchy through physical "stacking" rather than artificial shadows.

*   **The Layering Principle:** Place a `surface-container-lowest` card on top of a `surface-container-low` background. This creates a natural "lift" that is easier on the eyes than a drop shadow.
*   **Ambient Shadows:** For the 380px side panel and FAB, use a shadow with a 24px blur, 8px Y-offset, and 6% opacity using a tinted shadow color (`#17228f`). This mimics natural, ambient light.
*   **The "Ghost Border":** If a boundary is required for accessibility, use the `outline-variant` token at 15% opacity. Never use 100% opaque borders.
*   **Corner Radii:** A mandatory **12px (md)** radius is applied to all cards, bubbles, and inputs. The FAB uses **Full (9999px)** for a tactile, "button" feel.

---

## 5. Components

### Floating Action Button (FAB)
*   **Dimensions:** 56x56px.
*   **Styling:** Gradient fill (`primary` to `primary-container`).
*   **Elevation:** Ambient Shadow (Level 3). 
*   **Interaction:** On hover, the gradient should shift slightly in angle; on click, a subtle 2px scale-down effect.

### Side Panel (The Widget)
*   **Width:** 380px.
*   **Background:** `surface-container-lowest` (White) with 85% opacity and backdrop-blur.
*   **Header:** Asymmetric layout. Title-Md aligned left; close button (ghost style) aligned right. No divider line—use a `surface-container-low` background for the header area to separate it from the message thread.

### Chat Bubbles
*   **User:** `primary` background, `on-primary` text. 12px radius, but 4px radius on the bottom-right corner to "point" to the user.
*   **Support:** `surface-container-high` background, `on-surface` text. 12px radius, but 4px radius on the bottom-left corner.
*   **Spacing:** 8px between bubbles in a cluster; 16px between different speakers.

### Inputs & Textareas
*   **Background:** `surface-container-low`.
*   **States:** On focus, the background shifts to `surface-container-lowest` and a 2px `primary` "Ghost Border" (20% opacity) appears.
*   **Textareas:** Minimum height 120px for "large" variants. Placeholder text should be `outline` color, italicized for a "human" touch.

### Badges & Chips
*   **Priority (Low/Med/High):** Use soft-tints (10% opacity of the color) with bold text. (Gray / Orange / Red).
*   **Status (Open/In-Progress/Resolved):**
    *   **Open:** `primary-fixed` background with `on-primary-fixed` text.
    *   **In-Progress:** `tertiary-fixed` background with `on-tertiary-fixed` text.
    *   **Resolved:** `surface-variant` background with `on-surface-variant` text.
*   **Chips:** Selection chips should use the `secondary-container` token with a `sm` (4px) border radius for a "technical" contrast against the rounded widget.

---

## 6. Do’s and Don’ts

### Do
*   **Do** use vertical white space (24px, 32px) to separate content blocks instead of lines.
*   **Do** use semi-transparent backgrounds for floating elements to maintain a sense of place.
*   **Do** ensure all interactive elements have a minimum 44px tap target, even if the visual element is smaller.

### Don't
*   **Don't** use pure black `#000000` for text; use `on-surface` (#191c1e) for better readability.
*   **Don't** use high-contrast, 1px borders. If you feel you need a border, try a 4px padding increase or a subtle background tint first.
*   **Don't** use standard "drop shadows." All shadows must be diffused and tinted with the primary hue to maintain the "Glassmorphism" aesthetic.