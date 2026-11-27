# CLAUDE.md

## Project Overview

Racely landing page — a single-file HTML/CSS/JS marketing site for the Racely iOS app (race tracker for runners).

- **Stack**: Pure HTML + CSS + JS, no build system
- **File**: `index.html` (all styles and scripts inline)
- **Fonts**: Gloock (display) + Archivo (body), from Google Fonts
- **Hosted**: GitHub Pages at https://anansadiya94.github.io/racely/

## Design Context

### Users
Runners of all levels — from casual 5K participants to dedicated marathoners and ultra runners. Landing page visitors are discovering the app or looking for the App Store link.

### Brand Personality
Three words: **Precise. Earned. Steady.**

The intersection of a race timer's clarity, the quiet pride of a personal record, and the reliability of a trusted training partner. Motivating without being loud. Clean without being cold.

### Aesthetic Direction
- **Theme**: Light primary, dark secondary (user-toggleable, respects system preference)
- **Visual tone**: Refined precision. Numbers matter and should look important. Think timing boards, official race results — not sports marketing, not wellness dashboards.
- **Anti-references**: Generic health app (pastel cards, Apple Health aesthetic), social media (feeds, leaderboards), aggressive sports brand marketing
- **Font note**: Gloock replaced Cormorant Garamond (overused). Gloock has a single weight (400) and no italic, and `font-synthesis: none` is set, so don't give it other weights or `font-style: italic`. Emphasis in display type comes from color.

### Design Principles
1. **Numbers are the hero** — finish times, PRs, distances deserve typographic weight and presence
2. **Achievement, not activity** — race log, not training tracker. Design honors the effort of racing.
3. **Quiet confidence** — restrained color, generous space, clear hierarchy
4. **Personal over social** — every message is about *your* journey, not comparison
5. **Precision matters** — 3:28:27 ≠ 3:29:14. Sharp, legible data presentation

### Implementation Notes
- **Contrast tokens**: `--blue` (from the iOS app) is too light for small text or white-on-blue. Use `--blue-btn` + `--on-blue` for filled buttons and `--blue-text` for blue text under 24px. `--text-2`/`--text-3` are tuned to pass WCAG AA on every surface in both themes.
- **Theme**: the initial theme is set by an inline script in `<head>` (avoids a light flash). Scroll-reveal hiding is scoped to `.js` so content shows without JavaScript.
- **CSS order matters**: rules that override a component inside a media query (e.g. `.nav-menu-btn`, touch-target sizes) must come after that component's base rule.
