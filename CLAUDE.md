# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

**Tobolkometrie** is a static website project presenting scientific analysis of the Czech library community, specifically focusing on recipients of the prestigious Z.V. Tobolka award.

The project name derives from **Zdeněk Václav Tobolka** (1874-1951), a prominent Czech librarian and bibliographer whose legacy lives on through the award given for outstanding contributions to Czech librarianship.

## Project Type

- **Format**: Static HTML website with shared CSS design system
- **Language**: Czech (cs)
- **Hosting**: GitHub Pages
- **Framework**: None (pure HTML/CSS/vanilla JS)
- **CMS**: Decap CMS (formerly Netlify CMS)
- **Design System**: NTK Red accessible color scheme
- **Dependencies**: Decap CMS via CDN, GoatCounter analytics

## File Structure

```
tobolkometrie/
├── index.html              # Homepage (uses styles.css + page-specific layout)
├── metodika.html           # Methodology page (5-tobolka rating system)
├── drzitele.html           # Recipients database (156 records, searchable)
├── clanky.html            # Articles listing page
├── clanek.html            # Article detail template
├── styles.css             # Shared NTK red design system (MAIN STYLESHEET)
├── tobolka_data.json      # 156 recipient records (1995-2024)
├── CNAME                  # Custom domain configuration
├── admin/
│   ├── index.html         # Decap CMS admin interface
│   ├── config.yml         # CMS configuration
│   └── README.md          # Editor documentation (Czech)
├── content/
│   ├── articles/          # Article markdown files
│   ├── pages/             # Static page markdown files
│   └── recipients/        # Award recipient profiles (future)
├── images/
│   └── uploads/           # User-uploaded images
├── README.md              # Project documentation
├── CLAUDE.md              # This file
└── .gitignore             # Git ignore rules
```

## Architecture

### Content Management System (CMS)

**Decap CMS** provides a visual editor for non-technical users to manage content:

- **Admin Interface**: `/admin/` - Visual WYSIWYG editor accessible via GitHub OAuth
- **Content Storage**: Markdown files in `/content/` directory
- **Workflow**: Edit in CMS → Commit to GitHub → Auto-deploy via GitHub Pages
- **No Backend**: Completely static, uses GitHub as database

### Website Structure

The site consists of multiple HTML pages:

1. **index.html** - Homepage with hero, research areas, methodology
2. **clanky.html** - Articles listing with filtering
3. **clanek.html** - Article detail page (dynamic content loading)
4. **admin/** - CMS admin interface

Each page:
- Uses shared CSS variables for consistency
- Includes GoatCounter analytics
- Fully responsive (mobile-first)
- No build process required

### CSS Architecture

**IMPORTANT:** All pages must link to `styles.css` as the single source of truth for design system.

- **Shared Stylesheet** - `styles.css` contains NTK red design system used across all pages
- **CSS Variables** - Design tokens defined in `:root` for consistent theming
- **Generic Fonts** - Uses `font-family: sans-serif` and `font-family: serif` (no specific font stacks)
- **Responsive Design** - Mobile-first approach with breakpoints at 640px, 768px, 1024px
- **Grid System** - CSS Grid for card layouts, responsive column counts
- **High Contrast** - WCAG 2.1 AA compliant color contrasts
- **No External Dependencies** - All styles in styles.css, no CSS frameworks

### NTK Red Design System Variables

**Current color scheme (NTK Red - high contrast academic):**

```css
--primary: #C41E3A         /* NTK Red */
--primary-dark: #9B1528    /* Darker red for hover states */
--primary-light: #E63946   /* Lighter red for accents */
--primary-foreground: #ffffff
--secondary: #2C3E50       /* Dark blue-gray */
--background: #ffffff
--foreground: #1a1a1a      /* Nearly black text */
--muted: #f5f5f5           /* Light gray background */
--muted-foreground: #333333
--card: #ffffff
--border: #cccccc
--radius: 0.25rem          /* Smaller radius for sharper look */
--accent: #8B0000          /* Dark red accent */
```

**Typography:**
- Body: `sans-serif`, 16px, line-height 1.75, weight 400
- Serif headings: `serif`, weight 600
- High contrast links: 2-3px underline thickness

**Accessibility features:**
- 3px focus outlines with 2px offset
- High contrast link styling with thick underlines
- Hover states increase underline thickness
- 2px borders on form inputs (increases on hover/focus)

## Content Structure

### Pages

1. **index.html** - Homepage with hero section, research areas, about Z.V. Tobolka award, methodology
2. **drzitele.html** - Searchable database of 156 recipients (1995-2024) with Jára Cimrman easter egg
3. **metodika.html** - 5-tobolka rating system methodology (🍄 mushroom emoji scale)
4. **clanky.html** - Articles listing (Decap CMS powered)
5. **clanek.html** - Article detail page template

### Key Research Areas

The website presents six research domains:
1. Demografická analýza (Demographic analysis)
2. Publikační aktivita (Publication activity)
3. Trendy a vzorce (Trends and patterns)
4. Hodnocení přínosu (Impact assessment)
5. Databázové systémy (Database systems)
6. Statistická analýza (Statistical analysis)

### 5-Tobolka Rating System

Recipients are rated 1-5 "tobolky" (mushrooms 🍄) based on:
- **50%** - Přínos oboru (Contribution to field)
- **50%** - Celkový dojem (Overall impression)

**Scale:**
- 5 tobolky: Výjimečný, transformativní vliv (Exceptional, transformative impact)
- 4 tobolky: Vynikající, významný přínos (Outstanding, significant contribution)
- 3 tobolky: Pozoruhodný, konzistentní dopad (Remarkable, consistent impact)
- 2 tobolky: Standardní, splňuje očekávání (Standard, meets expectations)
- 1 tobolka: Minimální, kontroverzní (Minimal, controversial)

### Methodology Steps

1. Sběr dat (Data collection)
2. Analýza a kategorizace (Analysis and categorization)
3. Kvantitativní vyhodnocení (Quantitative evaluation)

### Easter Eggs

**Jára Cimrman** - Searching for "cimrman", "jára", or "jara" in drzitele.html reveals fictional 1896 recipient with golden badge styling.

## Development Commands

### Local Development

```bash
# Open in browser (macOS)
open index.html

# Start simple HTTP server (Python) - required for CMS testing
python3 -m http.server 8000
# Then visit: http://localhost:8000

# Start simple HTTP server (Node.js)
npx http-server -p 8000
```

**Note:** For testing the CMS locally, you need to run a local server. Opening `index.html` directly won't work for the admin interface.

### Testing Decap CMS Locally (Optional)

```bash
# Install Decap CMS proxy for local testing
npx decap-server

# In another terminal, start HTTP server
python3 -m http.server 8000

# Update admin/config.yml to enable local backend (uncomment line)
```

### Publishing

The site is published via GitHub Pages automatically:

```bash
# Make changes to HTML or content files
git add .
git commit -m "Description of changes"
git push origin main
```

GitHub Pages auto-deploys within 1-2 minutes.

### Content Editing

**Non-technical users** should use the CMS at `/admin/`:
1. Visit `https://tobolkometrie.cz/admin/`
2. Login with GitHub
3. Create/edit content visually
4. Click "Publish" - changes go live automatically

**Technical users** can edit Markdown files directly:
```bash
# Edit article
vim content/articles/2025-11-new-article.md

# Commit and push
git add content/articles/2025-11-new-article.md
git commit -m "Add new article"
git push origin main
```

## Editing Guidelines

### CSS Updates

**CRITICAL RULES:**
- All pages MUST link to `styles.css` as primary stylesheet
- DO NOT duplicate CSS variables or base styles inline
- Page-specific layout styles can be added in inline `<style>` tags
- Use generic fonts: `font-family: sans-serif` and `font-family: serif` only
- Never override design tokens - always use CSS variables from styles.css

**Pattern for page-specific styles:**
```html
<link rel="stylesheet" href="styles.css">
<style>
  /* Page-specific layout styles only */
  .hero { ... }
  .custom-layout { ... }
</style>
```

### Content Updates

When updating content:
- Maintain Czech language throughout
- Preserve semantic HTML structure
- Keep accessibility attributes (aria-hidden, aria-label, etc.)
- Use NTK red color scheme consistently
- Add icons with aria-hidden="true" for decorative SVGs
- Include external link indicators (↗) with aria-hidden="true"
- Ensure all sections remain in order

### Styling Updates

When modifying styles:
- Edit `styles.css` for design system changes (affects all pages)
- Use existing CSS variables for colors - never hardcode colors
- Maintain mobile-first responsive approach
- Test at breakpoints: mobile (<640px), tablet (640-1024px), desktop (>1024px)
- High contrast required: minimum WCAG 2.1 AA compliance
- Links must have 2px underlines, 3px on hover
- Focus states: 3px solid outline with 2px offset

### Adding New Sections

When adding new sections:
1. Follow existing section structure (`<section>` with appropriate classes)
2. Alternate `.section-alt` class for background variation
3. Use `.section-content` or `.section-wide` for max-width containers
4. Maintain consistent spacing with `section { padding: 4rem 1rem; }`
5. Add accessible footer navigation with sitemap structure

### Icon Guidelines

SVG icons are embedded inline from Lucide icon set style:
- 24x24 viewBox
- stroke-based (not fill)
- stroke-width="2"
- stroke-linecap="round"
- stroke-linejoin="round"
- Add `aria-hidden="true"` for decorative icons
- Use emoji icons in footer navigation (🏠 🔗 etc.) with aria-hidden

### Analytics

**GoatCounter integration (privacy-focused):**
- Script tag in `<head>`: `data-goatcounter="https://demoklion.goatcounter.com/count"`
- Tracking iframe in footer: `<iframe src="https://demoklion.goatcounter.com?access-token=TOKEN"></iframe>`
- Both required on every page

## GitHub Pages Configuration

The repository is configured to serve from:
- **Branch**: main
- **Path**: / (root)
- **File**: index.html
- **Custom Domain**: tobolkometrie.cz (requires DNS configuration at registrar)
- **CNAME file**: Contains domain name for GitHub Pages

**DNS Configuration (at Český hosting):**
- CNAME record: `www` → `demoklion.github.io`
- A records for apex domain → GitHub Pages IPs:
  - 185.199.108.153
  - 185.199.109.153
  - 185.199.110.153
  - 185.199.111.153

No Jekyll processing (static HTML only).

## Historical Context

The award and project focus on Czech library science:
- **Award Name**: Cena Z.V. Tobolky
- **Awarded Since**: 1995
- **Awarding Organization**: Svaz knihovníků a informačních pracovníků ČR (SKIP ČR)
- **Named After**: Zdeněk Václav Tobolka (1874-1951), director of Prague Municipal Library
- **Total Recipients**: 156 (1995-2024)

## Current Status (January 2025)

✅ **Completed:**
- NTK red accessible design system in styles.css
- Index page with hero, research areas, about section
- Metodika page with 5-tobolka rating system
- Drzitele database page with 156 searchable records
- Jára Cimrman easter egg
- GoatCounter analytics integration
- Accessible footer with sitemap navigation
- Decap CMS for article management
- JSON data structure for recipients

⏳ **Pending:**
- DNS configuration at Český hosting for custom domain
- Subpage consistency (metodika.html needs styles.css migration)
- Article system implementation via CMS

## Browser Support

Target browsers:
- Modern evergreen browsers (Chrome, Firefox, Safari, Edge)
- Mobile Safari (iOS)
- Mobile Chrome (Android)

No IE11 support required.
