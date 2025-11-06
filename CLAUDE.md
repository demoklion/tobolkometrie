# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

**Tobolkometrie** is a static website project presenting scientific analysis of the Czech library community, specifically focusing on recipients of the prestigious Z.V. Tobolka award.

The project name derives from **Zdeněk Václav Tobolka** (1874-1951), a prominent Czech librarian and bibliographer whose legacy lives on through the award given for outstanding contributions to Czech librarianship.

## Project Type

- **Format**: Single-page static HTML website
- **Language**: Czech (cs)
- **Hosting**: GitHub Pages
- **Framework**: None (pure HTML/CSS)
- **Dependencies**: None

## File Structure

```
tobolkometrie/
├── index.html          # Main single-page website
├── README.md           # Project documentation
└── CLAUDE.md          # This file
```

## Architecture

### Single-Page Application Structure

The website is built as a single HTML file with embedded CSS, structured as follows:

1. **Hero Section** - Introduction with project title and main CTAs
2. **About Section** - Explanation of Tobolkometrie as a discipline
3. **Research Areas** - Six key research areas displayed in card grid
4. **Award Information** - Details about Z.V. Tobolka award
5. **Methodology** - Three-step research methodology
6. **Footer** - Project credits and copyright

### CSS Architecture

- **CSS Variables** - Design tokens defined in `:root` for consistent theming
- **Responsive Design** - Mobile-first approach with breakpoints at 640px, 768px, 1024px
- **Grid System** - CSS Grid for card layouts, responsive column counts
- **No External Dependencies** - All styles embedded, no CSS frameworks

### Design System Variables

```css
--primary: #2563eb (blue)
--secondary: #64748b (slate)
--background: #ffffff (white)
--foreground: #0f172a (dark blue)
--muted: #cbd5e1 (light gray)
--border: #e2e8f0 (border gray)
--radius: 0.5rem (border radius)
```

## Content Structure

### Key Research Areas

The website presents six research domains:
1. Demografická analýza (Demographic analysis)
2. Publikační aktivita (Publication activity)
3. Trendy a vzorce (Trends and patterns)
4. Hodnocení přínosu (Impact assessment)
5. Databázové systémy (Database systems)
6. Statistická analýza (Statistical analysis)

### Methodology Steps

1. Sběr dat (Data collection)
2. Analýza a kategorizace (Analysis and categorization)
3. Kvantitativní vyhodnocení (Quantitative evaluation)

## Development Commands

Since this is a static HTML project with no build process:

### Local Development

```bash
# Open in browser (macOS)
open index.html

# Start simple HTTP server (Python)
python3 -m http.server 8000

# Start simple HTTP server (Node.js - requires installation)
npx http-server
```

### Publishing

The site is published via GitHub Pages. To update:

```bash
# Make changes to index.html
# Commit and push
git add index.html
git commit -m "Description of changes"
git push origin main
```

GitHub Pages automatically serves the site from the `main` branch.

## Editing Guidelines

### Content Updates

When updating content:
- Maintain Czech language throughout
- Preserve semantic HTML structure
- Keep accessibility attributes (aria-hidden, etc.)
- Ensure all sections remain in order

### Styling Updates

When modifying styles:
- Use existing CSS variables for colors
- Maintain mobile-first responsive approach
- Test at breakpoints: mobile (<640px), tablet (640-1024px), desktop (>1024px)
- Keep all styles embedded in `<style>` tag

### Adding New Sections

When adding new sections:
1. Follow existing section structure (`<section>` with appropriate classes)
2. Alternate `.section-alt` class for background variation
3. Use `.section-content` or `.section-wide` for max-width containers
4. Maintain consistent spacing with `section { padding: 4rem 1rem; }`

### Icon Guidelines

SVG icons are embedded inline from Lucide icon set style:
- 24x24 viewBox
- stroke-based (not fill)
- stroke-width="2"
- stroke-linecap="round"
- stroke-linejoin="round"

## GitHub Pages Configuration

The repository is configured to serve from:
- **Branch**: main
- **Path**: / (root)
- **File**: index.html

No Jekyll processing (static HTML only).

## Historical Context

The award and project focus on Czech library science:
- **Award Name**: Cena Z.V. Tobolky
- **Awarded Since**: 1995
- **Awarding Organization**: Svaz knihovníků a informačních pracovníků ČR (Czech Library Association)
- **Named After**: Zdeněk Václav Tobolka, director of Prague Municipal Library

## Future Enhancements

Potential additions (currently not implemented):
- Database page for award recipients (#drzitele currently placeholder)
- JavaScript for interactive features
- Search functionality
- Data visualization
- Multi-page structure

## Browser Support

Target browsers:
- Modern evergreen browsers (Chrome, Firefox, Safari, Edge)
- Mobile Safari (iOS)
- Mobile Chrome (Android)

No IE11 support required.
