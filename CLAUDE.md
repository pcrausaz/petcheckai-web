# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is a Hugo-based static website for the Pet Check AI app (petcheckai.com). It uses the Bigspring theme and supports multilingual content (English US and French).

## Commands

### Development
- `hugo server -D` - Start development server with drafts
- `hugo server --cleanDestinationDir` - Start server with clean destination

### Deployment
- `hugo deploy` - Deploy the site

### Build
- `hugo` - Build the static site (outputs to /public)

## Architecture

### Content Structure
- **Multilingual setup**: Content organized by language codes in `/content/`
  - `en-US/` - English (US) content
  - `fr-FR/` - French content
- **Page types**: Each language has identical structure with Home, FAQ, Support, Privacy, and EULA pages
- **Configuration**: hugo.toml defines language-specific menus and parameters

### Theme and layouts (current)
- The Bigspring theme is still declared in `hugo.toml` (it provides a few fallbacks), but every rendered template is overridden in `/layouts/`:
  - `_default/baseof.html` – base skeleton (head partials, header, main, footer, inline script)
  - `index.html` – home page, rendered entirely from `_index.md` front matter (banner/demo phone, features bento, service, app_features, disclaimer, call_to_action, help)
  - `_default/single.html` – text pages (FAQ, Support, Privacy, EULA) with a page header and a sticky table of contents
  - `partials/header.html`, `partials/footer.html`, `partials/download-badges.html`, `partials/icon.html` (inline SVG icons keyed by name)
  - `partials/style.html` compiles `assets/scss/style.scss`; `partials/script.html` holds the tiny mobile-nav toggle
- Design: "Daylight" – pale blue hero with a glow, white body, navy call-to-action; fonts Sora (display) + Manrope (body) from Google Fonts; accent `#2B5CE6` from the app icon. No Bootstrap, no Font Awesome.
- Hero phone: a CSS mock screen driven by `banner.demo` in the home front matter. Set `params.hero_screenshot` in `hugo.toml` to a real app capture (path under `/static`) to replace it.
- UI strings live in `/i18n/en-US.toml` and `/i18n/fr-FR.toml`.
- Text pages keep the page heading in front matter (`heading`) rather than an H1 in the markdown.

### Static Assets
- `/static/` - Files copied directly to site root
- `/assets/` - Processed assets
- **IMPORTANT**: Never edit files in `/public/` - they are generated

### Key Files
- `hugo.toml` - Main configuration with multilingual setup
- `/layouts/partials/header.html` - Navigation and language switcher
- `/content/*/images/` - Page-specific images per language
- `/data/` - Data files for Hugo
- `/assets/scss/style.scss` - Custom SCSS styles for the site

### Shortcodes
- `downloadapp` - App Store download link (requires updating with actual App Store ID)
- `downloadappbeta` - TestFlight beta download link
- `betastamp` - Visual "BETA" stamp with rotation styling
- `buymeacoffee` - Buy me a coffee widget integration
- `welcome-guide` - Welcome guide image gallery

### Custom Partials (Theme Support)
Created to support Bigspring theme requirements:
- `/layouts/partials/favicon.html` - Favicon and icon links
- `/layouts/partials/basic-seo.html` - Basic SEO meta tags
- `/layouts/partials/logo.html` - Site logo/brand display
- `/layouts/partials/script.html` - Inline mobile-nav script (overrides theme)
- Various analytics partials (gtm, matomo, baidu, plausible, counter)

## Development Notes

- Hugo minimum version: 0.128.0 (per theme requirements)
- Theme supports posts, shortcodes, related content, and comments
- Site uses unsafe HTML rendering enabled in goldmark configuration
- Caching configured for images in `:cacheDir/images`
- `static/app-ads.txt` is used for google Admob

## Theme Transition Notes

- Ananke → Bigspring (2025), then Bigspring styling replaced by the custom "Daylight" layouts and stylesheet (September 2026). The theme's CSS/JS plugins are intentionally not loaded.

### Troubleshooting
- If you see "template for shortcode not found" errors, check `/layouts/shortcodes/` directory
- Missing partials should be created in `/layouts/partials/` with at least placeholder content
