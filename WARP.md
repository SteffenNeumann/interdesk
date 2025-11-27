# WARP.md

This file provides guidance to WARP (warp.dev) when working with code in this repository.

## Project Overview

**interdesk** is a static marketing/consulting website built with vanilla HTML, CSS, and JavaScript. It's a German-language business site hosted on W3Schools Spaces for digital consulting services.

## Core Architecture

### Technology Stack
- **Frontend:** Pure HTML5, CSS3, vanilla JavaScript
- **CSS Framework:** W3.CSS from W3Schools CDN
- **Icons:** Font Awesome 4.7.0
- **Forms:** FormSubmit.co for contact form handling (sends to interdesk24@gmail.com)
- **Hosting:** W3Schools Spaces
- **No build process:** Direct HTML/CSS/JS files

### File Structure
```
interdesk/
├── index.html              # Main landing page
├── construction1.html      # Alternative/construction version of main page
├── datenschutz.html       # Privacy policy page (GDPR compliance)
├── newstyle.css           # Primary stylesheet (active)
├── styles.css             # Legacy/alternative stylesheet
├── README.md              # W3Schools template documentation
└── content/               # Images and assets (referenced but not in repo)
    ├── *.jpg             # Various consulting images
    ├── logo5.ico         # Favicon
    └── Avatar6.png       # Footer avatar
```

### Key Design Patterns

**CSS Variables:** Both stylesheets use CSS custom properties for consistent theming:
- Brand color: `--title-span-color: #7869E6` (purple)
- Font sizes defined as CSS variables (`--font-medium` through `--font-3x-large`)
- Transition speed: `--transition-fast: 0.5s`

**Layout Architecture:**
- Single-page sections with anchor navigation (#about, #consulting, #contact, #footer)
- Fixed footer height: 750px bottom margin on main content
- Mobile-first responsive with separate mobile navigation (side drawer)
- CSS classes: `.main-content`, `.container`, `.navigation`, `.hero`, `.c-card`, etc.

**Navigation System:**
- Desktop: Horizontal navigation bar with inline links
- Mobile: Hamburger menu triggering slide-in sidenav (`#mobile-sidenav`)
- JavaScript functions: `toggleMobileNavigation()`, `goToTop()`, `scroll()`

**Content Cards:**
- Alternating left/right layout using `.c-card` and `.c-card-right`
- Reveal animations on scroll using `.reveal` class
- Images loaded from `content\` directory (note: backslashes used, Windows-style paths)

## Common Development Tasks

### Local Development
```bash
# Open in browser (no build process required)
open index.html
# OR use local server for accurate testing:
python3 -m http.server 8000
# Then navigate to http://localhost:8000
```

### Testing Different Pages
```bash
open index.html           # Main landing page
open construction1.html   # Alternative version
open datenschutz.html     # Privacy policy
```

### Version Control Workflow
**Branch:** `main` (only branch in use)

Before starting work:
```bash
git pull
```

After finishing work:
```bash
git add .
git commit -m "Description of changes"
git push
```

## Important Notes

### Path Handling
- Image paths use Windows-style backslashes: `content\filename.jpg`
- When editing, maintain consistent path format with existing code

### Contact Form
- Uses FormSubmit.co service
- Endpoint: `https://formsubit.co/interdesk24@gmail.com`
- `index.html` has captcha enabled (`_captcha: true`)
- `construction1.html` has captcha disabled (`_captcha: false`)

### Stylesheet Differences
- **newstyle.css:** Active stylesheet linked in `index.html` and `construction1.html`
- **styles.css:** Used in `datenschutz.html` only
- Both contain nearly identical CSS with minor variations

### External Dependencies (CDN)
- W3.CSS: `https://www.w3schools.com/w3css/4/w3.css`
- W3 Color Library: `https://www.w3schools.com/lib/w3-colors-highway.css`
- Font Awesome: `https://cdnjs.cloudflare.com/ajax/libs/font-awesome/4.7.0/css/font-awesome.min.css`
- Google Fonts preconnect configured (but no specific font loaded via link)

### GDPR Compliance
- Comprehensive privacy policy in `datenschutz.html`
- German legal text for data protection (Datenschutzerklärung)
- Includes sections on hosting (W3Schools), contact forms, SSL/TLS, social media integrations

### Content Considerations
- All content in German
- Business contact: Steffen Neumann, Neuching, Germany
- Copyright footer: "© 2022 interdesk. All rights reserved."

## Code Style Guidelines

### HTML
- Use semantic HTML5 elements (`<main>`, `<section>`, `<nav>`, `<footer>`)
- W3.CSS utility classes extensively: `w3-container`, `w3-metro-light-blue`, `w3-margin-top`, etc.
- Inline JavaScript event handlers common: `onclick="functionName()"`
- Async script tags for performance

### CSS
- 60% width containers for main content (`.container`)
- Color scheme: Purple accent (#7869E6), light backgrounds, dark text
- Box shadows for depth: standard W3.CSS shadow patterns
- Smooth scroll enabled: `scroll-behavior: smooth` on html element

### JavaScript
- Vanilla JS only, no frameworks
- Functions defined in inline `<script async>` tags
- Common patterns: scroll handlers, navigation toggles, slideshow controls
- `reveal()` function adds `.active` class to elements on scroll for animations

## Deployment

This site is hosted on W3Schools Spaces. Changes pushed to the main branch should be reflected on the live site automatically (verify W3Schools integration settings).
