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

### Theme Bigspring (Current)
- Uses Bigspring Hugo theme from `/themes/bigspring/`
- Theme provides responsive layout with Bootstrap-based styling
- Custom layouts in `/layouts/` override theme defaults
- Custom shortcodes: betastamp, buymeacoffee, downloadapp, downloadappbeta, welcome-guide
- Custom partials created to support theme requirements 


### Static Assets
- `/static/` - Files copied directly to site root
- `/assets/` - Processed assets
- **IMPORTANT**: Never edit files in `/public/` - they are generated

### Key Files
- `hugo.toml` - Main configuration with multilingual setup
- `/layouts/partials/i18nlist.html` - Language switcher
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
- `/layouts/partials/social/share.html` - Social sharing placeholder
- `/layouts/partials/script.html` - Custom script loading (overrides theme)
- Various analytics partials (gtm, matomo, baidu, plausible, counter)
- Layout helper partials (preloader, tags, menu-contextual)

## Development Notes

- Hugo minimum version: 0.128.0 (per theme requirements)
- Theme supports posts, shortcodes, related content, and comments
- Site uses unsafe HTML rendering enabled in goldmark configuration
- Caching configured for images in `:cacheDir/images`
- `static/app-ads.txt` is used for google Admob

## Theme Transition Notes

### From Ananke to Bigspring
- **Completed**: Successfully transitioned from Ananke to Bigspring theme
- **Plugin Status**: CSS/JS plugins temporarily disabled due to missing Font Awesome and Bootstrap dependencies
- **Custom Styling**: Created simplified SCSS with basic styling to replace missing Bootstrap dependencies
- **All Shortcodes**: Working properly with new theme

### Known Issues & TODO
- [ ] Re-enable Font Awesome plugins when dependencies are available
- [ ] Update `/layouts/shortcodes/downloadapp.html:11` with actual App Store ID (replace `idXXXXXXXXXX`)
- [ ] Consider adding Bootstrap dependencies if advanced styling is needed
- [ ] Test all shortcodes in production environment

### Troubleshooting
- If you see "template for shortcode not found" errors, check `/layouts/shortcodes/` directory
- If CSS/JS plugins fail, they are likely commented out in `hugo.toml` - dependencies need to be installed first
- Missing partials should be created in `/layouts/partials/` with at least placeholder content