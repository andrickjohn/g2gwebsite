# Grins2Go Website | Coastal Premium Revamp

> [!IMPORTANT]
> **🚢 MESSAGE IN A BOTTLE: CONTINUING ON YOUR OTHER COMPUTER**
> 1. Open your terminal on the other machine.
> 2. `cd` into your project directory.
> 3. Run `git pull origin main` to get the latest Tailwind 4.0 setup and Hero section.
> 4. Run `npm install` to ensure the new Tailwind dependencies are ready.
> 5. Run `npm run dev` to pick up exactly where we left off.

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
