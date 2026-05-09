# Grins2Go Website | Coastal Premium Revamp

> [!IMPORTANT]
> **🚢 MESSAGE IN A BOTTLE — Last updated: 2026-05-09**
>
> **Status**: Foundation complete (Astro + Tailwind 4 + Cloudflare). Full migration plan written. **Blocked on 5 owner inputs** before building can continue.
>
> **To continue on another computer:**
> 1. `git pull origin main`
> 2. `npm install`
> 3. `npm run dev`
> 4. Read `PROGRESS.md` for full status
> 5. Read `PLAN.md` for the complete migration strategy
>
> **🔴 OWNER INPUT NEEDED (answer these to unblock the build):**
> 1. **Photos** — Where are your portfolio images? (local folder, Drive, Dropbox?)
> 2. **Reviews** — Export full review text from WordPress admin (Tools → Export → Testimonials). 250+ reviews need the body text, not just titles.
> 3. **Pricing** — Is the current site pricing still accurate?
> 4. **Domain** — Will this replace beachportraitsmaui.com?
> 5. **Booking** — Keep phone/email only, or add an online booking form?

---


This project is a high-performance revamp of [beachportraitsmaui.com](https://www.beachportraitsmaui.com/), moving from WordPress to **Astro + Cloudflare (SSR)**.

## 🌅 The "Coastal Premium" Design System

The site uses a boutique, high-end aesthetic inspired by luxury Maui resorts and fine-art photography.

### Color Palette (HSL Tokens in `global.css`)
- **Sand White** (`#FDFCF8`): Warm, organic base.
- **Deep Ocean Teal** (`#0D2F2F`): Sophisticated contrast for text and depth.
- **Sunset Gold** (`#E6B35E`): Elegant accent for calls to action.

### Typography
- **Headings**: *Cormorant Garamond* (Fine Serif) for an editorial, "luxe" feel.
- **Body**: *Outfit* (Modern Sans) for clarity and tech-forwardness.

---

## 🛠 Project State & Roadmap

- **Stack**: Astro 6.1, Tailwind-less (Vanilla CSS with HSL tokens), Cloudflare Adapter.
- **Infrastructure**: SSR configured for Cloudflare Pages.
- **Sync**: Git-connected to `andrickjohn/g2gwebsite`.

### Reference Files
- [PLAN.md](./PLAN.md): Detailed implementation strategy.
- [TASKS.md](./TASKS.md): Current progress and upcoming TODOs.
- [src/styles/global.css](./src/styles/global.css): Core design tokens and utilities.

---

## 🧞 Commands

| Command | Action |
| :--- | :--- |
| `npm install` | Installs dependencies |
| `npm run dev` | Starts local dev server at `localhost:4321` |
| `npm run build` | Build your production site to `./dist/` |
| `npm run preview` | Preview your build locally (Cloudflare emulation) |

---

## 🧑‍💻 Hand-off Note for Claude
The foundation is set. The **Hero Section** and **Design System** are implemented on the Home page. 
**Priority 1**: Build the `PhotoGrid.astro` component to handle high-res masonry galleries.
**Priority 2**: Migrate the Gallery pages (Family, Sunset, etc.) using the `src/pages/gallery` structure.
