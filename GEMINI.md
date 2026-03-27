# GEMINI.md - Coffee Timer (手沖職人指南) ☕

## Project Overview

**Coffee Timer** is a specialized web application designed for coffee enthusiasts using the **Tetsu Kasuya 4:6 Method** and **Flower Pouring** technique. It provides a highly visual, stage-based timer to ensure consistent extraction.

### Core Technologies
-   **Frontend**: [React 18](https://reactjs.org/) (via CDN), [TailwindCSS](https://tailwindcss.com/) (via CDN), [Babel Standalone](https://babeljs.io/).
-   **Visuals**: Procedural SVG Path generation (`generateFlowerPath`) and CSS Keyframe animations.
-   **Hosting**: [Firebase Hosting](https://firebase.google.com/docs/hosting) (coffee-timer.yooneko.com) and GitHub Pages.

---

## Architecture

This project uses a "Single-File React-in-HTML" architecture, eliminating the need for a complex build pipeline (npm/webpack) while maintaining modern component-based development.

### 1. Component Logic (Functional React)
-   **Timer Engine**: Uses `useEffect` and `setInterval` within the `App` component to track elapsed seconds.
-   **Brew Data**: Configuration for different weights (300ml vs 600ml) is stored in a `brewData` constant.
-   **Dynamic Diagrams**: The `PouringDiagram` component renders different SVG patterns (circle, petal, turbulence) based on the current stage's specific pouring technique.

### 2. UI/UX Patterns
-   **Auto-Scrolling**: Uses `stageRefs` (`useRef` array) and `scrollIntoView` to automatically keep the active brewing stage centered on screen.
-   **Branding**: Inherits the "YooNeko" design language with a soft shadow system (`yooneko-shadow`) and curated typography (Noto Sans TC + JetBrains Mono).
-   **Glassmorphism**: Sticky header uses `backdrop-blur-md` for a premium feel.

---

## Directory Structure

```text
coffee-timer/
├── public/              # Production Directory (Served by Firebase)
│   ├── index.html       # Main SPA (Full React + CSS code)
│   └── favicon.png      # High-res Branding & App Icon
├── index.html           # Root Redirect (For GitHub Pages compatibility)
├── firebase.json        # Redirects root to /public and defines headers
├── .firebaserc          # Target Firebase project mapping
└── GEMINI.md            # AI Developer Guide (This file)
```

---

## Technical Mechanisms

### 4:6 Method Calculation
The timer divides the total brew time into 5 stages of 45 seconds each.
-   **Stage 1 & 2 (40%)**: Focused on flavor balance (Acidity vs. Sweetness).
-   **Stage 3, 4, 5 (60%)**: Focused on body and strength.

### Procedure SVG (Flower Pouring)
`generateFlowerPath()` calculates a mathematical "flower" shape using polar coordinates to simulate the specialized pouring route, providing the user with a precise visual reference.

---

## Maintenance Guidelines for AI Agents

1.  **Single-File Integrity**: All React and CSS changes must remain within `public/index.html`. Do not attempt to split into multiple `.js` files unless a build process is introduced.
2.  **CDN Reliance**: If updating React or Tailwind, ensure the CDN links in the `<head>` remain valid and synchronized.
3.  **Modern Aesthetics**: Every new component should match the "YooNeko Premium" style—rounded corners (`rounded-2xl`), soft shadows (`yooneko-shadow`), and intentional spacing.
4.  **Responsiveness**: Always test the UI for mobile-width devices, as this tool is primarily used on phones next to a coffee scale.
5.  **Branding Consistency**: Use the established `Yoo` (#ff6b81) and `Neko` (#2d3436) brand colors in footers and links.

---

© 2026 YooNeko Platform Development.
