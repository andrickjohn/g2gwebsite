# Progress Tracker — Grins2Go Website Migration

> **Last Updated**: 2026-05-09 by Antigravity (Conversation 897bf872)
> **Repo**: https://github.com/andrickjohn/g2gwebsite.git
> **Stack**: Astro 6.1 + Tailwind 4 + Cloudflare Pages

---

## ✅ Done

- [x] Initialize Astro project with Cloudflare adapter — `06b83c1`
- [x] Establish "Coastal Premium" design system (Sand/Teal/Gold HSL tokens) — `7bf265f`
- [x] Build initial Hero section + Stats bar on index page — `7bf265f`
- [x] Connect GitHub remote (`andrickjohn/g2gwebsite`) — `0911d81`
- [x] Install Tailwind 4.0 and migrate index.astro to utility classes — `331d6a2`
- [x] Update README with project orientation and hand-off docs — `0911d81`
- [x] Create full migration plan (PLAN.md) — current commit

## 🔲 Blocked — Waiting on Owner Input

- [ ] **Photos**: Where are portfolio images stored? (local folder, Google Drive, etc.)
- [ ] **Reviews**: Need full review text exported from WordPress admin (250+ reviews, only titles captured so far)
- [ ] **Pricing**: Confirm current pricing is still accurate
- [ ] **Domain**: Will new site replace beachportraitsmaui.com?
- [ ] **Booking**: Keep phone/email only, or add online form?

## 📋 Next (Once Unblocked)

1. Create `DESIGN.md` (Coastal Premium design rules for any AI agent)
2. Create `CLAUDE.md` (agent instructions for Claude Code compatibility)
3. Build Navbar + Footer components
4. Build Hero component with real Maui imagery
5. Build PhotoGrid component with lightbox
6. Build ReviewCard + ReviewCarousel components
7. Assemble full Home page
8. Build Reviews page (needs review data export)
9. Build Pricing page
10. Build About page
11. Build 6 Gallery sub-pages (needs photos)
12. SEO + Schema.org structured data
13. Performance audit (target: Lighthouse 95+)
14. Cloudflare Pages deployment

## ⚠️ Known Issues

- WordPress site returns 403 on subpages when fetched programmatically (reviews, pricing, about, gallery pages blocked). Must export content from WP admin directly.
- `Welcome.astro` component still exists in `src/components/` but is no longer used. Can be deleted.

## 🔧 Key Decisions Made

| Decision | Choice | Rationale |
|---|---|---|
| CSS Framework | Tailwind 4.0 | AI velocity + automatic purging for performance |
| Design System | Custom DESIGN.md | More targeted than taste-skill for a photography site |
| AI Agent | Antigravity primary, Claude Code compatible | Antigravity can see the browser; CLAUDE.md for fallback |
| Hosting | Cloudflare Pages | Edge deployment, sub-50ms TTFB globally |
| Image Strategy | Astro `<Image />` | Auto WebP + responsive srcsets, no dependencies |
| JS Strategy | Zero libraries | IntersectionObserver only, no React/Vue overhead |
