# CLAUDE.md - AI Assistant Guide

This document provides context for AI assistants working with this repository.

## Project Overview

This is **jonasdenil.github.io**, a personal GitHub Pages portfolio website. It's a static single-page site built with HTML5, SASS, and jQuery, based on the "Strata" template by HTML5 UP.

**Live URL:** https://jonasdenil.github.io

## Repository Structure

```
jonasdenil.github.io/
├── index.html          # Main single-page HTML (all content lives here)
├── README.md           # Basic project description
├── LICENSE.md          # License placeholder
├── css/                # Compiled CSS stylesheets
│   ├── style.css       # Main compiled styles
│   ├── style-*.css     # Responsive breakpoint overrides
│   ├── skel.css        # Skel framework base
│   └── font-awesome.min.css
├── sass/               # SASS source files
│   ├── style.scss      # Main stylesheet source
│   ├── style-*.scss    # Responsive variants
│   ├── _vars.scss      # Variables (colors, fonts, sizing)
│   └── _mixins.scss    # Vendor prefix helpers
├── js/
│   ├── init.js         # Site initialization and interactivity
│   ├── jquery.min.js   # jQuery library
│   ├── jquery.poptrox.min.js  # Lightbox gallery plugin
│   └── skel.min.js     # Responsive framework
├── fonts/              # Font Awesome icon fonts
└── images/
    ├── avatar.jpg      # Profile image
    ├── bg.jpg          # Background image
    ├── fulls/          # Full-size gallery images
    └── thumbs/         # Gallery thumbnails
```

## Technology Stack

| Technology | Purpose |
|------------|---------|
| HTML5 | Semantic page structure |
| SASS/SCSS | CSS preprocessing with variables and mixins |
| jQuery 1.11+ | DOM manipulation and plugins |
| Skel.js | Responsive grid framework and breakpoints |
| Font Awesome | Icon library |
| poptrox | jQuery lightbox gallery plugin |

## Key Files

- **index.html** - The entire site content. Contains header, about section, portfolio gallery, contact form, and footer.
- **sass/style.scss** - Primary stylesheet source (~1142 lines). Edit this for styling changes.
- **sass/_vars.scss** - Color and typography variables. Primary accent: `#49bf9d`, secondary: `#1f1815`.
- **js/init.js** - Site initialization including Skel breakpoints, parallax effects, and gallery setup.

## Development Workflow

### No Build System

This project has no automated build tooling (no package.json, Webpack, or Gulp). Changes work as follows:

1. **HTML changes**: Edit `index.html` directly - changes are immediate
2. **JavaScript changes**: Edit `js/init.js` directly
3. **CSS changes**: Either:
   - Edit compiled CSS in `css/` directly (quick but not recommended)
   - Edit SASS in `sass/`, compile manually with `sass sass/style.scss css/style.css`

### SASS Compilation

If modifying styles via SASS, compile manually:

```bash
# Single file compilation
sass sass/style.scss css/style.css

# Watch mode (if making multiple changes)
sass --watch sass/:css/
```

### Responsive Breakpoints

The site uses Skel.js with these breakpoints (configured in `js/init.js`):

| Breakpoint | Max Width | Notes |
|------------|-----------|-------|
| xlarge | 1800px | |
| large | 1280px | |
| medium | 980px | |
| small | 736px | Touch disabled, no scaling |
| xsmall | 480px | |

## Page Sections

The index.html contains these main sections:

1. **Header** (`#header`) - Avatar and tagline
2. **Section One** - Bachelorproef project description (urban planning research)
3. **Section Two** - "Recent Work" portfolio gallery
4. **Section Three** - "Get In Touch" contact form
5. **Footer** (`#footer`) - Social links (GitHub, Email)

## Conventions

### HTML
- Use semantic HTML5 elements (`<header>`, `<section>`, `<article>`, `<footer>`)
- Images use `<article>` wrappers with `thumb` class for gallery items
- Icons use Font Awesome classes: `fa fa-[icon-name]`

### CSS/SASS
- Follow existing indentation (tabs)
- Use existing variables from `_vars.scss` for colors and fonts
- Use provided mixins for vendor prefixes
- Responsive styles go in breakpoint-specific files (style-medium.scss, etc.)

### JavaScript
- jQuery-based, using `$(document).ready()` pattern
- Skel configuration in `js/init.js` - modify breakpoints there
- Gallery uses poptrox with `usePopupNav: true` configuration

## Common Tasks

### Adding a Portfolio Item

In `index.html`, add within the `<section id="two">` gallery:

```html
<article class="6u 12u$(xsmall) work-item">
    <a href="images/fulls/[full-image].jpg" class="image fit thumb">
        <img src="images/thumbs/[thumb-image].jpg" alt="Description" />
    </a>
    <h3>Project Title</h3>
    <p>Project description.</p>
</article>
```

### Updating Social Links

Social links are in `#footer` section. Use Font Awesome icon classes:

```html
<li><a href="URL" class="icon fa-[icon-name]"><span class="label">Label</span></a></li>
```

### Changing Colors

Edit `sass/_vars.scss`:
- `$color-accent-bg` - Primary accent background (#49bf9d)
- `$color-accent-fg` - Primary accent foreground
- `$color-accent2-bg` - Secondary accent background (#1f1815)

## Deployment

GitHub Pages automatically deploys from the main branch. Simply push changes:

```bash
git add .
git commit -m "Description of changes"
git push origin main
```

## Known Limitations

- Contact form is non-functional (no backend)
- Portfolio images are placeholders (kitten images)
- No CSS minification/optimization
- No automated testing or linting

## Attribution

Based on "Strata" template by HTML5 UP (html5up.net) - CCA 3.0 licensed for personal and commercial use.
