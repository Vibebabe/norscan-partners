# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is the **Norscan Partners** website - a modern, professional corporate website for a Norwegian strategic business consulting firm. The site is a static single-page application built with vanilla HTML, CSS, and JavaScript.

**Live Site:** Hosted on Vercel at https://norscan-partners-ku0r5z4jv-vibebabes-projects.vercel.app
**Repository:** https://github.com/Vibebabe/norscan-partners

## Critical Deployment Workflow

**IMPORTANT:** This project is configured for automatic deployment from GitHub to Vercel.

**Every change MUST be committed and pushed to GitHub:**
```bash
git add .
git commit -m "Description of changes"
git push
```

Vercel will automatically detect the push and deploy the changes. Do NOT use `vercel` CLI commands unless explicitly requested - the auto-deployment from GitHub is the primary workflow.

## Project Structure

```
/
├── index.html              # Single-page website (all sections in one file)
├── styles.css              # All styling with CSS variables for theming
├── script.js               # Smooth scrolling and animations
├── vercel.json             # Vercel deployment configuration
└── images/
    └── partners/           # Partner profile photos (16 images)
```

## Architecture & Design System

### Color Scheme
The site uses a **green color palette** defined in CSS variables in `styles.css`:
- `--primary-color: #15543e` (dark green)
- `--secondary-color: #1e7e5c` (medium green)
- `--accent-color: #10b981` (bright green)
- Background colors have light green tints

**When changing colors:** Always modify the CSS variables in `:root` rather than individual color values throughout the stylesheet.

### Page Sections
The single-page layout consists of these main sections (in order):
1. **Navigation** - Fixed header with smooth scroll links
2. **Hero** - Main headline with CTA
3. **Stats** - 14 partners, 30+ years, 100+ clients
4. **About** - Company description with feature cards
5. **Expertise** - 6 service areas (Strategisk rådgivning, Eierskap og eierstyring, Kjøp og salg, Restrukturering, Kapital, Interimledelse)
6. **Method** - NorscanMetoden description
7. **Partners** - Grid of 16 partner profiles with photos
8. **Testimonials** - Client quotes
9. **Contact** - Contact information
10. **Footer** - Copyright and links

### Partner Data Structure
The partners section displays 16 partners with:
- Profile photo (120px circular with green border)
- Full name
- Title (usually "Partner")
- Brief description

**Partner images are stored in** `images/partners/` with filenames matching the pattern: `firstname-lastname.jpg`

When adding/updating partners:
1. Add image to `images/partners/`
2. Update HTML in the partners grid section
3. Image will automatically be styled via `.partner-image` CSS class

## Local Development

To preview changes locally:
```bash
python -m http.server 8000
```
Then visit `http://localhost:8000`

## Content Language

All content is in **Norwegian (Bokmål)**. When adding or modifying text, maintain Norwegian language consistency.
