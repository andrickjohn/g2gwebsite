# Grins2Go Website — Full Migration & Revamp Plan

Migrating [beachportraitsmaui.com](https://www.beachportraitsmaui.com/) from WordPress (Avada theme) to **Astro 6.1 + Tailwind 4 + Cloudflare Pages**. The new site must be stunning, luxury-tier, blazingly fast, and contain ALL existing content (especially 250+ reviews).

---

## Your Questions — Answered

### 1. Taste-Skill vs. Claude Design vs. Nothing?

> [!IMPORTANT]
> **Recommendation: Use a custom `DESIGN.md` file (inspired by taste-skill) rather than installing taste-skill directly.**

**Why not taste-skill directly?**
- Taste-skill is a generic "anti-slop" system prompt. It was designed for greenfield apps and dashboards — not photography portfolios.
- Its "anti-rules" (no centered hero, no 3-column grid) would actually fight against what works for a photography site where centered, full-bleed imagery IS the right choice.
- It's best as inspiration, not as a literal dependency.

**What I recommend instead:**
I will create a `DESIGN.md` file in your repo that captures the specific "Coastal Premium" rules for THIS project. Any AI agent (me, Claude Code, Cursor) that opens the project will read it and know exactly what to do and what NOT to do. This is more targeted and more effective than a generic skill file.

### 2. Claude Code vs. Everything From Here?

> [!IMPORTANT]
> **Recommendation: Do it all from here (Antigravity). Claude Code is not necessary.**

**Why?**
- I can write code, run your dev server, test in the browser, commit to git, and push — all in one conversation.
- Claude Code is a terminal-only agent. It can't see the site visually, which is critical for a photography portfolio.
- Adding Claude Code creates a coordination problem: two agents editing the same files without shared context.

**Where Claude Code WOULD help:**
- If you want to do quick edits on your other computer and I'm not available. In that case, the `DESIGN.md` and `CLAUDE.md` files I'll create will give Claude Code perfect context.

### 3. Continuity & Hand-off Strategy

I will create a `PROGRESS.md` file in the repo root that tracks:
- What's been done (with commit hashes)
- What's in progress
- What's next
- Known issues

Any agent (or you) can read this file and immediately know where to pick up.

---

## Open Questions

> [!WARNING]
> **Content I need from you before building:**
> 1. **Photos**: Do you have your portfolio images exported somewhere (Google Drive, Dropbox, local folder)? I need the actual high-res photos for the galleries.
> 2. **Reviews**: The WordPress site has 250+ review titles but the full review text is blocked behind 403 errors. Can you export them from your WordPress admin? (Tools → Export → Posts, filtered to testimonials)
> 3. **Pricing**: Is the pricing on the current site still accurate? (Complimentary session fee for ≤7 people, $299 starting; Groups 8-12 at $175 session fee, $899 starting)
> 4. **Domain**: Will the new site go live at `beachportraitsmaui.com` or a new domain? This affects Cloudflare DNS setup.
> 5. **Booking Flow**: Currently you use phone (808-242-1424) and email (info@beachportraitsmaui.com). Do you want to add an online booking form or keep it phone/email?

---

## Architecture

```
grins2go_website/
├── CLAUDE.md                  # Agent instructions for Claude Code
├── DESIGN.md                  # Visual design system & rules
├── PROGRESS.md                # Living progress tracker
├── astro.config.mjs           # Astro + Cloudflare + Tailwind
├── src/
│   ├── styles/global.css      # Tailwind 4 @theme tokens
│   ├── layouts/
│   │   └── Layout.astro       # Base HTML shell + SEO
│   ├── components/
│   │   ├── Navbar.astro       # Sticky nav with glassmorphism
│   │   ├── Hero.astro         # Full-bleed hero with parallax
│   │   ├── PhotoGrid.astro    # Masonry gallery component
│   │   ├── ReviewCard.astro   # Individual review display
│   │   ├── ReviewCarousel.astro # Featured reviews rotator
│   │   ├── PricingTier.astro  # Pricing card component
│   │   ├── Footer.astro       # Contact info + links
│   │   └── SEOHead.astro      # Meta tags, OG, schema.org
│   ├── pages/
│   │   ├── index.astro        # Home (hero, featured gallery, reviews, CTA)
│   │   ├── reviews.astro      # All 250+ reviews
│   │   ├── pricing.astro      # Pricing tiers
│   │   ├── about.astro        # Team & Hyatt location
│   │   └── gallery/
│   │       ├── index.astro    # Gallery hub
│   │       ├── families.astro
│   │       ├── couples.astro
│   │       ├── sunset.astro
│   │       ├── hyatt.astro
│   │       ├── mornings.astro
│   │       └── wailea.astro
│   └── data/
│       ├── reviews.json       # All 250+ reviews as structured data
│       └── pricing.json       # Pricing tiers as structured data
├── public/
│   ├── images/                # Optimized portfolio photos
│   └── favicon.svg
└── wrangler.jsonc             # Cloudflare Pages config
```

---

## Proposed Changes

### Phase 1: Foundation (Agent Files + Design System)

#### [NEW] CLAUDE.md
Agent instructions file for Claude Code compatibility. Contains project context, file structure, coding conventions, and what NOT to do.

#### [NEW] DESIGN.md
The "Coastal Premium" design bible. Replaces taste-skill with project-specific rules:
- Color palette (Sand, Teal, Gold) with exact hex/HSL values
- Typography rules (Cormorant Garamond headings, Outfit body)
- Layout principles (full-bleed imagery, generous whitespace)
- Anti-patterns (no stock photo overlays, no generic blue CTAs, no busy backgrounds)
- Component patterns (how cards, grids, and sections should look)

#### [NEW] PROGRESS.md
Living progress tracker with sections: Done, In Progress, Next, Known Issues, Commit Log.

#### [MODIFY] [global.css](file:///Users/andrickjohn/Projects/grins2go_website/src/styles/global.css)
Already has Tailwind 4 `@theme` tokens. Will add responsive breakpoint utilities and animation keyframes.

---

### Phase 2: Core Components

#### [NEW] Navbar.astro
- Transparent on hero, solid on scroll
- Glassmorphism backdrop blur
- Mobile hamburger with slide-in menu
- Phone number (808-242-1424) always visible

#### [NEW] Hero.astro
- Full-viewport height with your actual Maui beach photo
- Parallax scroll effect on the background
- Elegant serif headline with gold accent
- Two CTAs: "View Gallery" and "Book a Session"

#### [NEW] PhotoGrid.astro
- Masonry layout using CSS columns (no JS library needed — fastest possible)
- Lightbox on click (using a lightweight `<dialog>` element, no dependency)
- Lazy loading with blur-up placeholder
- Accepts a `category` prop to filter images

#### [NEW] ReviewCard.astro
- Clean card with 5-star display, quote text, reviewer name, location
- Subtle entrance animation on scroll

#### [NEW] Footer.astro
- Phone, email, Hyatt Regency location
- Gallery category links
- Social links (if any)

---

### Phase 3: Pages

#### [MODIFY] [index.astro](file:///Users/andrickjohn/Projects/grins2go_website/src/pages/index.astro)
Sections in order:
1. **Hero**: Full-bleed Maui sunset with headline
2. **Trust Bar**: 15+ Years · 2k+ Families · 5.0 Rating
3. **Featured Gallery**: 6-image grid from best shots
4. **"It's All We Do" Section**: Migrated specialist copy from current site
5. **Featured Reviews**: 3 rotating testimonials
6. **Groups CTA**: "Did You Say Groups?" section with dedicated call-to-action
7. **Footer**: Contact + navigation

#### [NEW] reviews.astro
- All 250+ reviews displayed
- Filter by type (families, couples, anniversaries, groups)
- Paginated or infinite scroll for performance

#### [NEW] pricing.astro
- Two pricing tiers: Couples/Families and Groups
- Clean comparison layout
- Phone CTA for booking

#### [NEW] about.astro
- Team section (John & Brenda)
- Hyatt Regency Maui retail location details
- "15,000+ sessions" credential

#### [NEW] gallery/*.astro
- 6 gallery sub-pages matching current categories
- Each uses PhotoGrid component with category filtering

---

### Phase 4: Data Migration

#### [NEW] src/data/reviews.json
All 250+ reviews extracted from the WordPress site, structured as:
```json
[
  {
    "title": "Just magical",
    "text": "Full review text...",
    "author": "Yvonne Taylor",
    "location": "Carrollton, TX",
    "rating": 5,
    "category": "family"
  }
]
```

#### [NEW] src/data/pricing.json
Pricing tiers as structured data for easy updates.

---

### Phase 5: Performance & SEO

#### [NEW] SEOHead.astro
- Dynamic meta title/description per page
- Open Graph images (auto-generated or curated per page)
- Schema.org LocalBusiness + Review structured data (critical for Google rich results)
- Canonical URLs

#### Performance Targets
| Metric | Target |
|---|---|
| Lighthouse Performance | 95+ |
| First Contentful Paint | < 1.5s |
| Largest Contentful Paint | < 2.5s |
| Total Blocking Time | < 200ms |
| Cumulative Layout Shift | < 0.1 |
| Total CSS Bundle | < 15KB |

#### Performance Strategy
- **Images**: Astro `<Image />` component for automatic WebP conversion + responsive srcsets
- **Fonts**: `font-display: swap` + preconnect to Google Fonts
- **CSS**: Tailwind purges unused styles automatically
- **JS**: Zero client-side JavaScript except for lightweight scroll animations (IntersectionObserver, no library)
- **Hosting**: Cloudflare Pages edge deployment (sub-50ms TTFB globally)

---

### Phase 6: Deployment

#### Cloudflare Pages Setup
1. Connect GitHub repo (`andrickjohn/g2gwebsite`) to Cloudflare Pages
2. Build command: `npm run build`
3. Output directory: `dist/`
4. Add custom domain when ready

---

## Verification Plan

### Automated
- `npm run build` — verify Cloudflare compatibility (no Node.js-only APIs)
- Lighthouse CLI audit on built pages
- Check all images render and lazy-load correctly

### Visual QA
- Browser testing: Desktop (1440px), Tablet (768px), Mobile (375px)
- Gallery lightbox functionality
- Navigation on all pages
- Review display and filtering

### Manual
- Confirm all 250+ reviews are present and accurate
- Confirm pricing matches current site
- Confirm phone number and contact info are correct
- Test on actual mobile device

---

## Execution Order

| Step | Description | Effort |
|---|---|---|
| 1 | Create CLAUDE.md, DESIGN.md, PROGRESS.md | 10 min |
| 2 | Build Navbar + Footer components | 20 min |
| 3 | Build Hero component with real imagery | 15 min |
| 4 | Build PhotoGrid + lightbox | 30 min |
| 5 | Build ReviewCard + carousel | 15 min |
| 6 | Assemble Home page | 20 min |
| 7 | Build Reviews page (needs review data) | 20 min |
| 8 | Build Pricing page | 15 min |
| 9 | Build About page | 15 min |
| 10 | Build Gallery sub-pages (needs photos) | 30 min |
| 11 | SEO + Schema.org | 15 min |
| 12 | Performance audit + fixes | 15 min |
| 13 | Cloudflare Pages deployment | 10 min |
