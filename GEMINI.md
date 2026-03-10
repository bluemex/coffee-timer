# Coffee Timer - GEMINI Context

## Project Overview
This project is a specialized web-based coffee brewing timer and guide, specifically designed for the **4:6 Method** combined with a **Flower Pouring** technique. It provides a step-by-step visual and timed interface to help users achieve consistent pour-over results.

- **Primary Technologies:** React 18 (via CDN), Tailwind CSS (via CDN), Babel Standalone, Lucide-like SVG icons.
- **Key Features:**
  - Automated stage-based timer (5 stages of 45 seconds each).
  - Visual pouring diagrams for different techniques (center-to-circle, center-only, petal-to-center, turbulence).
  - Presets for different brew sizes (20g/300ml and 35g/600ml).
  - Dynamic UI that scrolls to the active stage.

## Architecture
The application is a **single-file web application** (`index.html`). 
- **Frontend Logic:** Contained within a `<script type="text/babel">` block using React hooks (`useState`, `useEffect`, `useRef`).
- **Styling:** Handled via Tailwind CSS utility classes and custom CSS in the `<style>` tag.
- **Icons & Diagrams:** Procedural SVGs and custom path generators (e.g., `generateFlowerPath`).

## Building and Running
As a static HTML file using CDN-hosted libraries, no traditional build step is required.

- **Development:** Simply open `index.html` in any modern web browser.
- **Local Server (Optional):** You can use a simple static server for a better development experience:
  ```bash
  # Using Python
  python -m http.server 8000
  
  # Using Node.js (npx)
  npx serve .
  ```

## Development Conventions
- **Component Structure:** Functional components with hooks.
- **Styling:** Use Tailwind CSS classes directly in the JSX.
- **Icons:** Add new icons to the `Icon` component mapping if needed.
- **Brew Data:** Brewing parameters (powder, water, stages) are defined in the `brewData` object within the `App` component.
- **Language:** The UI is primarily in Traditional Chinese (`zh-TW`).

## Project Structure
- `index.html`: The entire application (HTML, CSS, JS).
- `.git/`: Version control history.
