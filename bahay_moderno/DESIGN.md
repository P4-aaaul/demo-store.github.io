# Design System Specification: The Artisanal Inventory

## 1. Overview & Creative North Star
**The Creative North Star: "The Digital Concierge"**

This design system moves away from the cold, spreadsheet-heavy aesthetics of traditional inventory management. Instead, it draws inspiration from the tactile warmth of a high-end Filipino boutique cafe. The goal is to make the user feel like a curator rather than a data entry clerk.

We break the "software template" look through **Intentional Asymmetry** and **Tonal Depth**. By utilizing a high-contrast typography scale and overlapping surface layers, we create an editorial layout that feels bespoke. The system prioritizes breathing room (whitespace) and soft transitions to reduce the cognitive load of managing complex stock levels.

---

## 2. Colors & Surface Architecture

### The Palette
We utilize a sophisticated range of ambers and earth tones to ground the experience in a "human-centered" warmth.

*   **Core Accents:** `primary` (#865300) for high-importance actions; `primary_container` (#D4870E) for brand moments and hero accents.
*   **Neutral Foundations:** `background` (#FCF9F5) serves as our canvas. For deep-contrast elements like sidebars, we use `on_background` (#1C1C1A) to provide an authoritative anchor.
*   **Functional Tones:** `tertiary` (#516446) for success/restock states; `error` (#BA1A1A) for low-stock alerts.

### The "No-Line" Rule
Traditional UI relies on 1px borders to separate content. **In this system, 1px solid borders are prohibited for sectioning.** 
Boundaries must be defined through:
1.  **Background Shifts:** Place a `surface_container_low` card on a `surface` background.
2.  **Shadow Depth:** Use elevation to imply boundaries.
3.  **Negative Space:** Use the spacing scale to create "invisible" gutters.

### The Glass & Gradient Rule
To ensure the UI feels premium:
*   **Floating Elements:** Modals and dropdowns should use `surface_container_lowest` with a 12px `backdrop-blur`. This allows the warm background tones to bleed through, softening the interface.
*   **Signature Gradients:** For primary CTAs, use a subtle linear gradient from `primary` to `primary_container`. This adds a "lithographic" quality that flat colors cannot achieve.

---

## 3. Typography
We use **Plus Jakarta Sans** as our sole typeface. Its geometric yet friendly curves strike the balance between professional precision and approachable warmth.

*   **Display (Editorial Moments):** Use `display-lg` (3.5rem) for main dashboard metrics or store titles. This creates a bold, "magazine" feel.
*   **Headlines (Navigation):** `headline-md` (1.75rem) should be used for section titles. Pair this with generous top margins to allow the typography to breathe.
*   **Body (Utility):** `body-lg` (1rem) for general content. We optimize for legibility with a slightly increased line height (1.6) to keep the "non-technical" feel.
*   **Labels (Data):** `label-md` (0.75rem) in All Caps with +0.05em tracking for table headers and metadata.

---

## 4. Elevation & Depth: Tonal Layering

We convey hierarchy through **Tonal Layering** rather than structural lines.

### The Layering Principle
Think of the UI as stacked sheets of fine handmade paper.
*   **Level 0 (Background):** `surface` (#FCF9F5).
*   **Level 1 (Sections):** `surface_container_low`.
*   **Level 2 (Active Cards):** `surface_container_lowest` (Pure White).

### Ambient Shadows
When a "floating" effect is required (e.g., a "New Item" modal), use the following shadow spec:
*   **Shadow Color:** Hex `on_surface` at 6% opacity.
*   **Blur:** 32px to 48px.
*   **Offset:** Y: 8px.
This mimics natural, ambient light rather than a harsh digital drop shadow.

### The "Ghost Border" Fallback
If a container requires a border for accessibility, use the **Ghost Border**: `outline_variant` (#D8C3AF) at **15% opacity**. Never use 100% opaque borders.

---

## 5. Components

### Buttons
*   **Primary:** Fully rounded (pill), `primary` background, `on_primary` text. Use a subtle inner glow (top-down) for a tactile feel.
*   **Secondary:** `secondary_container` background with `on_secondary_container` text.
*   **Ghost:** No background, `primary` text. Reserved for low-emphasis actions.

### Input Fields
*   **Styling:** 12px internal padding. `surface_container_highest` background.
*   **Focus State:** 2px ring using `primary_container` (#D4870E). No harsh black outlines.
*   **Shape:** `DEFAULT` (1rem/16px) radius to maintain the friendly, rounded aesthetic.

### Cards & Tables
*   **Table Rows:** 48px height. Forbid horizontal divider lines. Use a `surface_container_low` hover state to highlight rows.
*   **Inventory Cards:** Use `16px` (DEFAULT) corner radius. Place item imagery in a slightly recessed container (`surface_dim`) to create depth.
*   **Status Chips:** Use `tertiary_container` (Sage) for "In Stock" and `error_container` (Rose) for "Low Stock." Ensure text remains high-contrast using the `on_container` tokens.

### Specialized Component: The "Stock Indicator"
Instead of a standard progress bar, use a wide, rounded "Ambient Bar" using `secondary_fixed_dim` as the track and `primary` as the fill. This feels more like a lifestyle app than a database.

---

## 6. Do's and Don'ts

### Do:
*   **Do** use asymmetrical margins (e.g., larger left margins on headers) to create an editorial layout.
*   **Do** lean into "Warmth"—if a layout feels too "techy," increase the whitespace and check the `background` token.
*   **Do** use `Plus Jakarta Sans` bold weights for numbers; inventory counts should feel like a design feature.

### Don't:
*   **Don't** use pure black (#000000). Use `on_background` (#1C1C1A) for all dark elements.
*   **Don't** use sharp 90-degree corners. Everything in this system follows the **Roundedness Scale** (Minimum 8px, Standard 16px).
*   **Don't** use standard table dividers. Use vertical spacing and background shifts to separate data points.