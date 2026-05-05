# Grins2Go Website Revamp

Revamping the current WordPress-based photography site [beachportraitsmaui.com](https://www.beachportraitsmaui.com/) into a high-performance, premium Astro site hosted on Cloudflare.

## User Review Required

> [!IMPORTANT]
> **Git Remote**: Please create a new repository on GitHub/GitLab and provide the URL. I will then add it as a remote so we can sync your progress.

> [!TIP]
> **Design Vibe**: For the portfolio, we used a dark, executive theme. For **Beach Portraits Maui**, I recommend a "High-End Coastal" aesthetic:
> - **Primary**: Warm White / Sand (`#FDFCF8`)
> - **Secondary**: Deep Ocean Teal or Emerald (`#0D2F2F`)
> - **Accents**: Soft Sunset Gold (`#E6B35E`)
> - **Typography**: A mix of a premium Serif (e.g., *Cormorant Garamond*) and a clean Sans-serif (e.g., *Outfit*).

## Proposed Changes

### Foundation & Setup

#### [MODIFY] [astro.config.mjs](file:///Users/andrickjohn/Projects/grins2go_website/astro.config.mjs)
Configure the Cloudflare adapter for SSR (Server-Side Rendering) to handle dynamic galleries or contact forms in the future.

#### [NEW] [global.css](file:///Users/andrickjohn/Projects/grins2go_website/src/styles/global.css)
Establish the "Coastal Premium" design system with HSL tokens for colors, fluid typography, and consistent spacing.

### Component Architecture

#### [NEW] [Navbar.astro](file:///Users/andrickjohn/Projects/grins2go_website/src/components/Navbar.astro)
Sticky navigation with glassmorphism and subtle scroll effects.

#### [NEW] [Hero.astro](file:///Users/andrickjohn/Projects/grins2go_website/src/components/Hero.astro)
High-impact image section with parallax scroll and refined typography.

#### [NEW] [PhotoGrid.astro](file:///Users/andrickjohn/Projects/grins2go_website/src/components/PhotoGrid.astro)
A masonry or bento-style gallery component optimized for high-resolution images.

### Content Migration

#### [MODIFY] [index.astro](file:///Users/andrickjohn/Projects/grins2go_website/src/pages/index.astro)
Rebuild the landing page with structured sections:
1. Hero (Maui Sunset / Family Portrait)
2. Strategic Value Proposition (Why Grins2Go?)
3. Featured Gallery (Families, Couples, Sunset)
4. ROI/Testimonials (The "Beach Portraits Maui" Experience)
5. Pricing Tiers (Migrated from current site)

## Verification Plan

### Automated Tests
- `npm run build` to verify Cloudflare compatibility.
- Lighthouse/Performance checks for image optimization (using Astro's `<Image />` component).

### Manual Verification
- Review responsive layouts across mobile and desktop.
- Verify gallery interactions and image loading states.
