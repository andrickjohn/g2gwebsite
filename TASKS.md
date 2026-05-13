# Tasks: Grins2Go Website Revamp

> Last updated: 2026-05-13

## ✅ Complete

- [x] Initialize Git repository + Cloudflare adapter
- [x] Scaffold directory structure
- [x] Install Tailwind 4.0 via `@tailwindcss/vite`
- [x] Volcanic Luxury design system (global.css — charcoal/ivory/silver tokens)
- [x] Core Component Library
    - [x] `Navbar.astro` — dark gradient, glassmorphism scroll, logo, tagline bar
    - [x] `Footer.astro` — corrected address, no personal names
    - [x] `HeroSlideshow.astro` — 6-slide crossfade, click-to-advance
    - [x] `PhotoGrid.astro` — flexbox grid, category filtering, lightbox
    - [x] `Reviews.astro` — carousel + grid modes
- [x] Page Build
    - [x] Home page (hero, trust bar, specialists, morning, gallery preview, reviews, groups, CTA)
    - [x] Gallery page (111+ images, 8 category filters)
    - [x] Pricing page (2 tiers, FAQ accordion)
    - [x] Reviews page (284 reviews grid)
    - [x] About page (company story, differentiators)
- [x] Data pipeline
    - [x] WordPress XML → `reviews.json` (284 entries)
    - [x] WordPress uploads → `gallery.json` (111+ curated images)
- [x] Brand refinements
    - [x] Gold → Silver/Platinum palette
    - [x] Headline: "The Best Thing We Did on Maui."
    - [x] Ken Burns removed → crossfade only
    - [x] Groups gallery expanded to 15 images

## 🔴 Next Session — Fix These First

- [ ] Fix faded hero backgrounds on Pricing & Gallery pages
- [ ] Fix head cutoff on hero images (audit all `object-position` values)
- [ ] Fix logo visibility in navbar (too hard to see against bright images)
- [ ] Fix "Fast Fun Professional" specialist image cropping

## 🟡 Upcoming

- [ ] Repeat Customers section (~5 families, user will provide photos)
- [ ] Hidden booking form (post-phone-call follow-up)
- [ ] Mobile responsive polish
- [ ] WebP image conversion + srcset
- [ ] SEO structured data refinements
- [ ] Final Lighthouse performance audit
- [ ] Cloudflare Pages deployment
