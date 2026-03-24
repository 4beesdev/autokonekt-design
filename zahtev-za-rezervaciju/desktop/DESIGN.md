# Design System Strategy: Technical Precision & Tonal Depth

## 1. Overview & Creative North Star

### The Creative North Star: "The Precision Engineer"
This design system is built upon the philosophy of **Precision Engineering**. We are moving away from the "template" look of generic automotive apps to create a high-end, editorial experience. The aesthetic balances the heavy, industrial reliability of a professional garage with the sleek, technical interface of a modern diagnostic computer.

To achieve this, the system rejects standard rounded corners and thin divider lines. Instead, it utilizes **Angular Intentionality** (the signature clipped corner) and **Tonal Layering**. We create structure through depth and color shifts rather than borders, resulting in a UI that feels carved from solid material—trustworthy, premium, and technically superior.

---

## 2. Colors

The color palette is a high-contrast interplay between deep, nocturnal voids and high-visibility technical accents.

### Color Roles
- **Primary & Container (`#00222d`, `#003949`):** These are your "Foundation" colors. They represent the professional, deep-blue automotive environment.
- **Secondary (`#006e02`, `#72d860`):** These are "Action" colors. Use the vibrant green exclusively for progress, success, and primary interactions.
- **Tertiary (`#c2e8ff`, `#2f7da0`):** These represent "Data." Use these for technical readouts, secondary information, and highlights.
- **Surface Tiers:** Use the `surface-container` scale to build depth. 

### The "No-Line" Rule
**Explicit Instruction:** 1px solid borders are strictly prohibited for sectioning. Boundaries between content must be defined solely through:
1.  **Background Color Shifts:** Placing a `surface-container-low` card against a `surface` background.
2.  **Shadow Depth:** Using ambient light to define edges.
3.  **Negative Space:** Using the 16pt and 24pt spacing tokens to create logical groupings.

### The "Glass & Gradient" Rule
To add "soul" to the technical layout:
- **Hero Sections:** Use a subtle linear gradient from `primary` (#00222d) to `primary-container` (#003949) at a 135-degree angle.
- **Floating Elements:** For overlays or navigation bars, use **Glassmorphism**. Apply a `surface` color at 70% opacity with a `20px` backdrop blur.

---

## 3. Typography

The typography uses **Manrope** to convey a clean, bold, and authoritative voice.

*   **Display (L/M/S):** Reserved for hero titles and high-impact automotive stats. Use `bold` weight with `-0.02em` letter spacing to feel "engineered."
*   **Headline & Title:** Used for card headers and section titles. These provide the editorial structure.
*   **Body (LG/MD):** Set in `medium` weight for maximum readability against dark backgrounds.
*   **Label (MD/SM):** Used for technical specs, wrench-time data, and small metadata.

The hierarchy is intentionally dramatic; large display type sits adjacent to small, precise labels to create a "technical manual" editorial feel.

---

## 4. Elevation & Depth

We avoid the "flat" look by treating the UI as a series of physical layers.

### The Layering Principle
Depth is achieved by "stacking" surface tiers. 
- **Base:** `surface` (#f3faff)
- **Secondary Level:** `surface-container-low` (#e5f6ff)
- **Top Interaction Level:** `surface-container-highest` (#bce9fe)

### Ambient Shadows
When an element must "float" (like a primary action button or a modal), use an **Ambient Shadow**:
- **Color:** `on-surface` (#001f29) at 6% opacity.
- **Blur:** 32px to 48px.
- **Spread:** -4px.
This creates a soft lift that feels like natural light in a showroom, not a digital drop shadow.

### The "Ghost Border" Fallback
If contrast ratio requirements (WCAG) demand a border, use a **Ghost Border**:
- Token: `outline-variant` (#c1c7cc) at **15% opacity**. It should be felt, not seen.

---

## 5. Components

### The Signature Shape
All primary components (Buttons, Badges, Hero Headers) must utilize the **Clipped Corner** logic.
- **Style:** A 45-degree cut on the top-right and bottom-left corners (or as specified in brand assets).
- **Radius Scale:** All `border-radius` tokens are set to `0px` to maintain this sharp, technical edge.

### Buttons
- **Primary:** Clipped-corner shape. Background: `secondary` (#006e02). Text: `on-secondary` (#ffffff).
- **Secondary:** Clipped-corner shape. Background: `primary-container` (#003949). Ghost border optional.
- **Tertiary:** Text-only, using `primary` color in `label-md` bold, all-caps.

### Cards & Lists
- **Forbid Dividers:** Do not use lines to separate list items. Use a background shift of 2% or 12px of vertical whitespace.
- **Status Cards:** Use the secondary colors (`#efd567` for warning, `#72d860` for healthy) as a 4px vertical "accent stripe" on the left edge of the card.

### Technical Input Fields
- Use `surface-container-low` for the input fill. 
- Active state is indicated by a 2px `secondary` (#72d860) bottom-border only.

---

## 6. Do's and Don'ts

### Do:
- **Do** use intentional asymmetry. Align a large headline to the left and a small technical label to the far right.
- **Do** use "Breathing Room." Allow the `24` spacing token (6rem) to exist between major content blocks.
- **Do** use the vibrant green (`#72d860`) sparingly as a high-precision "laser" accent.

### Don't:
- **Don't** use standard rounded corners (e.g., 4px or 8px). It dilutes the "Auto Konekt" brand identity.
- **Don't** use 100% black. Always use the `primary` navy-teal for dark backgrounds to maintain tonal depth.
- **Don't** stack more than three levels of surface containers. It leads to visual "mush." Keep the hierarchy lean.

### Accessibility Note
While we use tonal layering, ensure that the contrast between text (`on-surface`) and its immediate background meets a minimum of 4.5:1. When using the vibrant green on light backgrounds, always verify legibility.