## 1. Interactive Recipe Scaler & Ingredient Checklist

    Core focus: Form inputs, state calculation, dynamic DOM rendering, and localStorage.

    What to build: A single-recipe card where users adjust a serving multiplier (e.g., 0.5x, 1x, 2x, 3x or custom servings) and ingredient quantities update smoothly. Include checkboxes for ingredients and step-by-step cooking instructions so users can track progress.

    Refresher win: Great practice parsing numbers safely, formatting fractions/decimals cleanly, and persisting checked/serving state across reloads.

## 2. Responsive Kan-Ban / Task Triage Board

    Core focus: CSS Grid/Flexbox layout, drag-and-drop or keyboard/button moves, and state transitions.

    What to build: A three-column board (To Do, In Progress, Done) with priority tags, a filter bar (by priority or search text), and the ability to add, move, or delete cards.

    Refresher win: Tests how quickly you remember event delegation, array filtering/mapping, and keeping UI state synchronized with underlying data.

## 3. Live Weather & Air-Quality Dashboard

    Core focus: fetch() with async/await, loading/error states, and data-driven UI updates.

    What to build: A city search or preset-location dashboard pulling from a free weather API (like Open-Meteo). Display current conditions, a multi-day forecast strip, and a unit toggle (°C / °F).

    Refresher win: Sharpens API response handling, graceful empty/error states, and building clean cards and badges from JSON data.

## 4. Accessible Theme & Typography Playground

    Core focus: CSS custom properties (--var), clamp() fluid sizing, contrast checking, and prefers-color-scheme / prefers-reduced-motion.

    What to build: A live sample landing page or editorial article paired with a collapsible control drawer where you tweak primary/surface colors, font pairings, border radius, and spacing scale—plus a live contrast ratio readout for text/background pairs.

    Refresher win: Reinforces modern CSS architecture and accessibility fundamentals (focus rings, semantic landmarks, contrast) that often get glossed over in quick prototypes.

    ### Core Architecture & Features
    #### 1. Semantic HTML Layout (Two Distinct Zones)
    **Preview Canvas (<main>):** A realistic sample page containing a hero banner, navigation bar, feature cards, body copy, form inputs, buttons (primary, secondary, disabled), and a blockquote or alert box. Having varied UI elements lets you immediately see where a theme breaks down.

    Control Drawer (<aside>): A collapsible sidebar or floating panel with native form controls (<input type="color">, <input type="range">, <select>, <fieldset>). Using <label> elements properly and adding keyboard shortcuts (like Esc to close the drawer) gives you clean accessibility practice right away.

    #### 2. CSS Custom Properties & Fluid Sizing
    Design Tokens on :root: Define variables for --bg-surface, --bg-elevated, --text-primary, --text-muted, --accent, --radius, --font-heading, --font-body, and --space-unit.

    Fluid Type Scale with clamp(): Set your base font size or scale ratio in JS/CSS so headings scale smoothly across mobile and desktop viewports without dozens of media queries.

    System Preference Hooks: Include a Light / Dark / System toggle that respects @media (prefers-color-scheme: dark) by default, plus a motion toggle wired to @media (prefers-reduced-motion: reduce).
    
    #### 3. JavaScript Logic (Where the Refresher Really Kicks In)Live Variable Injection: Listen for input events on your controls and update tokens via document.documentElement.style.setProperty('--accent', value).

    WCAG Contrast Ratio Calculator: Convert selected hex colors to relative luminance and calculate the contrast ratio between --text-primary and --bg-surface (and button text vs. --accent). Display a live badge showing AA Pass ($\ge 4.5:1$), AAA Pass ($\ge 7:1$), or Fail.

    Preset Themes & Randomizer: Include 3–4 curated presets (e.g., Editorial Paper, High-Contrast Brutalist, Midnight Slate) and a "Generate Accessible Pair" button that picks random colors until they pass AA contrast.
    Export CSS Snippet: A "Copy CSS Variables" button that reads current token values, formats a clean :root { ... } block, and copies it via navigator.clipboard.writeText().
    
    

## 5. Personal Finance & Subscription Tracker

    Core focus: Array reduce(), category breakdowns, form validation, and visual bars/charts (using HTML/CSS or <canvas> / SVG).

    What to build: A tracker where users log recurring bills or expenses by category and billing cycle (monthly vs. annual), normalize everything to a monthly cost, and view spending share by category.

    Refresher win: Exercises clean data modeling, currency formatting (Intl.NumberFormat), and turning numbers into clear visual summaries.