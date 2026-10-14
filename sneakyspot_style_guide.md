# SneakySpot 20 Questions - Style Guide

This document outlines the visual identity and design system for the "SneakySpot 20 Questions" web application. The design is heavily inspired by vibrant street art, pop-art aesthetics, and comic book styles, specifically referencing the mural art provided in the original project scope.

## 1. Core Aesthetic Philosophy

The visual language of SneakySpot is characterized by:
*   **Vibrancy:** High-contrast, saturated colors.
*   **Playfulness:** Comic-style elements, irregular shapes, and slight rotations.
*   **Tactility:** Heavy black borders, hard drop shadows, and visual depth.
*   **Cultural Context:** Prominent use of Bengali typography integrated into a modern, funky layout.

## 2. Color Palette

The color system relies on a bold set of primary and secondary colors, usually set against a deep blue background or accompanied by stark black lines.

### Primary Backgrounds
*   **Deep Blue Base:** `#1e3a8a` (Tailwind `blue-900`) - Used for the main body background, often overlaid with a subtle grid or gradient.
*   **Gradient Dark:** `#3b0764` (Tailwind `purple-950`) - Used in conjunction with Deep Blue for the main container background (`linear-gradient(135deg, #1e3a8a 0%, #3b0764 100%)`).

### Functional / Accent Colors (The "Sneaky" Palette)
These colors are used for buttons, panels, text strokes, and decorative elements.

*   **Sneaky Yellow:** `#facc15` (Tailwind `yellow-400`) - Primary accent, used for prominent text, call-to-action buttons, and the scrollbar thumb.
*   **Sneaky Red:** `#ef4444` (Tailwind `red-500`) - Used for negative actions ("No"), errors, alerts, and text shadows.
*   **Sneaky Green:** `#10b981` (Tailwind `emerald-500`) - Used for positive actions ("Yes"), success states, and correct guesses.
*   **Sneaky Cyan:** `#06b6d4` (Tailwind `cyan-500`) - Used for question panels and decorative SVG elements.
*   **Sneaky Purple:** `#8b5cf6` (Tailwind `violet-500`) - Used for neutral/unknown actions ("Don't Know").
*   **Sneaky Orange:** `#f97316` (Tailwind `orange-500`) - Used for probabilistic actions ("Sometimes").
*   **Sneaky Pink:** `#ec4899` (Tailwind `pink-500`) - Used occasionally as an alternate background for variety.

### Neutrals
*   **Black:** `#000000` - Critical for the comic-book style. Used for all heavy borders (`3px` or `4px`), text strokes, text colors on light backgrounds, and hard drop shadows.
*   **White:** `#ffffff` - Used for primary text on dark backgrounds and as a background for contrasting elements (like the "Powered by" badge).

## 3. Typography

The typographic hierarchy relies on a clean, modern Bengali sans-serif font paired with a playful English font for specific branding elements.

### Primary Font (Bengali & English UI)
*   **Font Family:** `Hind Siliguri`, sans-serif
*   **Usage:** All main text, headings, buttons, and questions.
*   **Weights:** Regular (400), SemiBold (600), Bold (700). The UI primarily utilizes the **Bold** weight for maximum impact and readability against the complex background.

### Secondary/Accent Font (English)
*   **Font Family:** `Bangers`, cursive (or similar comic-style display font)
*   **Usage:** Specifically for the "SneakySpot" brand name within the "Powered by" badge to add a pop-art feel.

### Text Styling Techniques
*   **Main Title (20 প্রশ্ন):** Uses a specific "Text Stroke" effect.
    *   Fill: `#facc15` (Yellow)
    *   Stroke: `-webkit-text-stroke: 2px black`
    *   Shadow: `text-shadow: 4px 4px 0px #ef4444` (Hard Red Shadow)

## 4. UI Components and Styling (The "Comic Border" System)

Almost all interactive and container elements utilize the "Comic Border" system to achieve the desired tactile, pop-art look.

### The "Comic Border" Class
This is the foundational style for panels and buttons.
*   **Border:** `3px solid black` (or `4px` for larger panels).
*   **Shadow (Pop):** `box-shadow: 6px 6px 0px 0px rgba(0,0,0,1)` (Hard, non-blurred offset).
*   **Radius:** Generally `rounded-xl` or `rounded-2xl` depending on the element size.

### Interaction States
*   **Hover:** Buttons usually change to a slightly lighter or darker shade of their base color (handled via Tailwind `hover:` utility).
*   **Active (Click):** When clicked, elements appear to depress into the page.
    *   `transform: translate(4px, 4px)` (Moves down and right)
    *   `box-shadow: 2px 2px 0px 0px rgba(0,0,0,1)` (Shadow shrinks to simulate closeness to the background).

### Specific Element Implementations

*   **Main Game Container:** Uses the `main-container-bg` gradient, `rounded-2xl`, and the `comic-border`.
*   **Buttons:** Standardized with `comic-border`, bold text (`font-bold`), large padding (`py-3`, `py-4`), and centered Flexbox content (often pairing text with FontAwesome icons).
*   **Question Panel:** Rotated slightly (`transform: rotate(1deg)`) dynamically to look like a placed card. Uses alternating vibrant background colors.
*   **"Powered By" Badge:** Small pill shape (`rounded-full`), white background, black text, thin black border (`border-2`), and rotated counter-clockwise (`-rotate-2`).

## 5. Animation & Motion

Animations are used sparingly but effectively to draw attention and provide feedback.

*   **Gentle Pulse (`animate-pulse-gentle`):** A slow scaling animation (100% -> 105% -> 100% over 2s). Used on the "Start" button and the final Guess text to draw the eye.
*   **Slide In/Out:** Used for transitioning between questions. The question panel slides in from the right (`slideInRight`) to simulate drawing a new card.
*   **Confetti:** A canvas-based particle system triggered upon a correct guess. It utilizes the Sneaky Palette colors and simulates falling paper.

## 6. Background Textures and Graphics

The background is not purely solid, preventing the design from feeling flat.

*   **Grid Pattern:** A CSS linear gradient is used on the `body` to create a subtle, semi-transparent white grid pattern (`40px x 40px` spacing) over the deep blue.
*   **Decorative SVGs (`bg-graphic`):** Large, low-opacity (15%) geometric shapes and text (like the circle with "চা" or the square with "বিপদ এখানেই") are placed absolutely behind the main container to mimic the cluttered, layered feel of the reference mural art.