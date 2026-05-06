# myAlfred Website — Source Code

**Live site:** https://www.myalfred.com  
**Captured:** 2026-05-07

---

## Tech Stack

| Layer | Technology |
|---|---|
| Frontend framework | Next.js (App Router) |
| Styling | Tailwind CSS v3.3.3 + custom CSS |
| Fonts | Inter, Poppins, Raleway, Prompt, Quicksand (Google Fonts) |
| Backend / CMS | WordPress (Yoast SEO, REST API) |
| CDN / Media | cdn-prod.myalfred.me |

---

## Project Structure

```
Myalfred/
├── index.html              ← Homepage HTML (server-rendered Next.js output)
├── blog.html               ← Blog page HTML
├── robots.txt              ← Crawler rules
├── sitemap_index.xml       ← Sitemap index (links to page/post/category sitemaps)
│
└── assets/
    ├── css/
    │   ├── 1850702b8dd10b4a.css   ← Main stylesheet (Tailwind base + custom styles, ~98KB)
    │   ├── 431944509084d071.css   ← Component-level styles (~11KB)
    │   └── a6dc42564bc74e46.css   ← Additional overrides (~2KB)
    │
    ├── js/
    │   └── chunks/                ← Next.js code-split JS bundles
    │       ├── webpack-*.js           Next.js module loader
    │       ├── polyfills-*.js         Browser polyfills
    │       ├── main-app-*.js          App bootstrap
    │       ├── layout-*.js            Shared layout (header, footer)
    │       ├── page-*.js              Homepage-specific logic
    │       ├── f58c171e-*.js          Large dependency bundle (~639KB)
    │       ├── fd9d1056-*.js          Dependency bundle (~169KB)
    │       └── [numbered chunks]      Feature-split bundles
    │
    └── img/
        ├── about/
        │   └── footerEllipse.svg
        ├── common/
        │   ├── sms.svg
        │   └── supportIcon.svg
        ├── landing/membership/
        │   └── blue-ribbon.png
        └── others/
            ├── appStore.svg
            ├── googlePlay.svg
            └── AppGallery.svg
```

---

## Key Notes for Edits

### Making content/UI changes
- The HTML in `index.html` and `blog.html` is the **compiled, server-rendered output** — it reflects what Next.js generates at build time.
- To make permanent changes, edits should be made in the **Next.js source repo** (not these compiled files directly), then rebuilt and deployed.
- These files are useful for understanding the current DOM structure, class names, and layout.

### Styling
- The site uses **Tailwind CSS utility classes** — most visual styling is done via class names directly in the HTML (e.g. `text-xl`, `bg-white`, `flex`, `gap-4`).
- Custom/brand styles are layered on top in the CSS files under `assets/css/`.
- The main CSS file (`1850702b8dd10b4a.css`) includes both the full Tailwind base and all custom rules.

### Images / Media
- Product and marketing images are served from the CDN: `https://cdn-prod.myalfred.me/media/assets/`
- App store badges, icons, and SVGs are served from `/assets/img/` on the main domain.

### Pages found in sitemap
| URL | Description |
|---|---|
| https://www.myalfred.com/ | Homepage |
| https://www.myalfred.com/blog/ | Blog listing |

---

## How to Share Changes

1. Make edits to the relevant files in this folder.
2. Zip the folder: `zip -r myalfred-changes.zip Myalfred/`
3. Share the zip with the tech team along with a description of what changed.

Or push to a shared Git repo and open a PR against the main Next.js source.
