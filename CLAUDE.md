# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Project Overview

This is the landing page for V2er, a native mobile client for the V2EX community. It's built as a static site using Astro framework with TailwindCSS for styling. The site is entirely in Chinese (zh-CN) and showcases the mobile app's features, user reviews, FAQs, and related products.

## Development Commands

**Install dependencies:**
```bash
npm install
```

**Start dev server:**
```bash
npm run dev
# Server runs on http://localhost:4321 by default
```

**Build for production:**
```bash
npm run build
# Runs astro check (type checking) before building
```

**Preview production build:**
```bash
npm run preview
```

**Type checking only:**
```bash
npx astro check
```

## Architecture

### Directory Structure
- `src/pages/` - Page routes (currently single page: index.astro)
- `src/layouts/` - Base HTML layout templates
- `src/components/` - Reusable Astro components (Navbar, Hero, Features, FAQ, Reviews, Footer, etc.)
- `src/styles/` - Component-specific CSS files plus base.css (global styles and CSS variables)
- `public/` - Static assets (images, icons, fonts)

### Tech Stack
- **Astro 4.16+** - Static site generator with zero JS by default
- **TailwindCSS 3.4+** - Utility-first CSS framework
- **TypeScript** - Using strict configuration (astro/tsconfigs/strict)
- **Font Awesome 6.5** - Icons loaded via CDN
- **Google Fonts** - Inter font family

### Key Architecture Patterns

1. **Single Page Application:**
   - All content lives on `index.astro`
   - Components are rendered server-side during build
   - No client-side JavaScript by default (pure static HTML/CSS)

2. **Component Structure:**
   - Each section (Hero, Features, FAQ, etc.) is a separate `.astro` component
   - Components are self-contained with their own styles imported
   - Shared styles in `base.css` define CSS variables and common classes

3. **Styling Approach:**
   - Mix of TailwindCSS utility classes and custom CSS
   - CSS variables defined in `:root` for theming (--accent, --text-primary, etc.)
   - Component-specific styles in separate CSS files (hero.css, features.css, etc.)
   - Dark theme by default (black background, white text)

4. **Design System:**
   - Custom accent color: `#333343`
   - System font stack with Apple system fonts
   - Consistent use of gradient text effects for section titles
   - Glassmorphism effects with backdrop filters
   - Smooth hover transitions and animations

### Layout Pattern
The main layout (`Layout.astro`) provides:
- Meta tags for SEO and social sharing
- Chinese language setting (`lang="zh-CN"`)
- CDN links for Font Awesome and Google Fonts
- Global base styles
- Dark theme by default

## Important Conventions

1. **Language:** All user-facing content must be in Chinese (Simplified)
2. **Responsive Design:** Mobile-first approach with desktop enhancements
3. **Performance:** Minimal JavaScript, optimized static assets
4. **No Client-Side JS:** Unless explicitly needed, keep the site static
5. **Astro Components:** Use `.astro` files for components, not React/Vue unless required

## Styling Guidelines

- Use TailwindCSS utilities for layout and basic styling
- Use custom CSS files for complex animations and component-specific styles
- Maintain consistency with existing gradient text effects
- Keep dark theme aesthetic (black backgrounds, white/gray text)
- Use CSS variables from `base.css` for theming

## External Assets

- **Icons:** Font Awesome loaded from cdnjs.cloudflare.com
- **Fonts:** Inter from Google Fonts
- **Images:** Stored in `public/image/` directory
- **App Store Links:** Connected to real app listings on Apple App Store and Google Play

## External Links
- App Store: https://apps.apple.com/app/id1596137027
- Play Store: https://play.google.com/store/apps/details?id=me.ghui.v2er
- GitHub: https://github.com/v2er-app
- Telegram: https://t.me/v2er_app
