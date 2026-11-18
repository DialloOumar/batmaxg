# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a static HTML website for Batmex Group (construction, heavy equipment & mining logistics, fiscal stamps, industrial supply) in Guinea. Deployed via GitHub Pages to www.batmexgroup.com (`CNAME`).

## Pages

- `index.html` — home: hero video, four sectors, fleet band, process, about, partners, contact form
- `fleet.html` — **equipment catalogue 2026** (nav: "Fleet"). Machine data lives in the `FLEET` array in the page script; cards and spec dialogs render from it. Deep link a machine with `fleet.html#m-<id>`.
- `catalogue.html` — **supply catalogue** (nav: "Supplies"): PPE, PVC & piping, consumables, steel, tools. Products live in the `SUPPLIES` array; visitors build a request list sent via WhatsApp/email.
- `img/catalogue/` — WebP images extracted from the 2026 equipment catalogue PDF

Keep the header/drawer/footer markup identical across pages (it is duplicated in each file), and keep fleet figures (48 machines + 45 trucks on contract, 8,000 t/day, 118 km, 32 machines + 300 trucks ready) in sync between `index.html` and `fleet.html`.

## Architecture

- **Multi-page, no shared includes**: Each page is self-contained with its own embedded CSS and JavaScript
- **Bilingual EN/FR**: Elements carry `data-en` / `data-fr`; the choice is stored in `localStorage` (`batmex_lang`)
- **No build process**: The site can be served directly from any web server or opened in a browser
- **Responsive design**: Mobile-first approach with CSS Grid and Flexbox
- **Vanilla JavaScript**: No external frameworks or dependencies

## Key Components

- **Header/Navigation**: Fixed header with mobile hamburger menu
- **Hero Section**: Animated landing area with statistics cards
- **Services Section**: Grid-based service cards with hover effects
- **Interactive Features**: Smooth scrolling, mobile menu toggle, scroll-based animations

## Development Commands

Since this is a static HTML project, there are no build commands. To work with the project:

- **View the site**: Open `index.html` directly in a web browser
- **Live development**: Use any static file server (e.g., `python -m http.server` or VS Code Live Server extension)
- **No dependencies**: No package.json, node_modules, or build tools required

## Styling Approach

- **CSS-in-HTML**: All styles are embedded in the `<style>` tag
- **CSS Custom Properties**: Uses CSS variables for consistent theming
- **Modern CSS**: Utilizes Grid, Flexbox, backdrop-filter, and CSS animations
- **Color Scheme**: Warm off-white (#FAF8F5) and near-black (#0c0c0e) with orange accents (#FF5A1F, #F7931E); fonts Sora + Hanken Grotesk, icons Material Symbols Rounded

## JavaScript Features

- Mobile menu toggle functionality
- Smooth scrolling navigation
- Dynamic header background on scroll
- Intersection Observer for scroll-based animations
- Event delegation for navigation links

## Responsive Breakpoints

- Mobile: max-width 768px
- Desktop: Above 768px
- Uses CSS Grid with auto-fit for flexible layouts