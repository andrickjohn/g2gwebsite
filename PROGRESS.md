# Progress Tracker — Grins2Go Website Migration

> **Last Updated**: 2026-05-13 by Antigravity
> **Repo**: https://github.com/andrickjohn/g2gwebsite.git
> **Stack**: Astro 6.1 + Tailwind 4 + Cloudflare Pages
> **Dev Server**: `nvm use 22 && npm run dev` → `localhost:4321`

---

## ✅ Done

- [x] Initialize Astro project with Cloudflare adapter
- [x] Install Tailwind 4.0 via `@tailwindcss/vite`
- [x] Establish "Volcanic Luxury" design system (Charcoal/Ivory/Silver-Platinum tokens)
- [x] Connect GitHub remote (`andrickjohn/g2gwebsite`)
- [x] Parse WordPress XML exports → `reviews.json` (284 reviews) + `gallery.json` (111+ images)
- [x] Copy uploads to `public/uploads/` for web access
- [x] Build Layout.astro — base HTML shell, Schema.org LocalBusiness, OG tags, counter script
- [x] Build Navbar — persistent dark gradient, logo, glassmorphism scroll, mobile menu, tagline bar
- [x] Build Footer — corrected address (200 Nohea Kai Dr), no personal names
- [x] Build HeroSlideshow — 6-slide crossfade, click-to-advance, pip navigation, rotating quotes
- [x] Build PhotoGrid — flexbox grid, category filtering, native dialog lightbox, head-safe cropping
- [x] Build Reviews component — carousel mode + grid mode, star ratings
- [x] Build Homepage — hero, trust bar, specialists, morning sessions, gallery preview, reviews, groups CTA, booking CTA
- [x] Build Gallery page — full filterable grid, 111+ images across 8 categories
- [x] Build Pricing page — two tiers, FAQ accordion, phone CTA
- [x] Build Reviews page — all 284 reviews in grid
- [x] Build About page — company story, differentiators, no personal names
- [x] Gold → Silver/Platinum palette swap
- [x] Headline → "The Best Thing We Did on Maui."
- [x] Remove Ken Burns (jerky) → clean crossfade only
- [x] Groups gallery expanded to 15 images (5+ people each)
- [x] Fix footer CTA headline → "Ready to Make Memories That Last Forever?"
- [x] Navbar dark gradient for readability over any hero image
- [x] Tagline "Maui's Premier Beach Portrait Photographers" in navbar

## 🔴 Needs Fixing (Next Session)

- [ ] **Faded hero backgrounds** — Pricing & Gallery page hero backgrounds are too faded (opacity-30 may still be too low). Need to increase visibility while maintaining text readability.
- [ ] **Head cutoff** — Several page hero images still crop heads. Need `object-position: center 25%` audit across all hero sections. Also verify the "Fast Fun Professional" specialist image shows full subjects.
- [ ] **Logo visibility** — Logo in navbar is hard to see against bright hero images. May need a larger logo, a persistent dark bar, or a white outline/glow on the logo itself.

## 🟡 Upcoming Features

- [ ] **Repeat Customers section** — User will provide ~5 photogenic repeat family examples. Build "They Keep Coming Back" section with multi-year comparison cards.
- [ ] **Hidden Booking Form** — Form sent directly to prospects after phone call. Not visible on site.
- [ ] **Mobile polish** — Verify all sections on iPhone/iPad viewports.
- [ ] **WebP conversion** — Convert gallery images to WebP for performance.
- [ ] **Responsive images** — Add `srcset` for different screen sizes.

## ⚠️ Known Issues

- Node 22+ required (`nvm use 22` before running dev server)
- CSS `@apply` does NOT work in component `<style>` blocks (Tailwind 4 + Astro limitation) — use inline classes or manual CSS properties
- Filename typo: `Portait` (missing 'r') in `Maui-Beach-Wailea-Portait-003-06-L.jpg` — this is the ACTUAL filename, do not "fix" it
- One group image uses lowercase `l` suffix: `Group-Portrait-003-06-l.jpg` — case-sensitive

## 🔧 Key Decisions Made

| Decision | Choice | Rationale |
|---|---|---|
| CSS Framework | Tailwind 4.0 | AI velocity + automatic purging for performance |
| Design System | "Volcanic Luxury" — Charcoal/Silver/Ivory | Dark premium feel, silver over gold per owner preference |
| Brand Voice | No individual names, no toddlers | Company identity, ideal client = affluent family w/ teens |
| Hero Headline | "The Best Thing We Did on Maui." | Client-voice testimonial, Maui-specific |
| Hero Animation | Crossfade only (no Ken Burns) | Ken Burns caused inconsistent zoom + jerky snap-back |
| Hosting | Cloudflare Pages | Edge deployment, sub-50ms TTFB globally |
| JS Strategy | Zero libraries | IntersectionObserver only, no React/Vue overhead |
