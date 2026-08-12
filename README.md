# Portfolio Site

A static one-page portfolio for junior Unity / gameplay programming roles. Plain HTML, CSS, and JS — no build step, no framework, no backend.

## File structure

```
index.html          all page content
css/styles.css        all styling (design tokens at the top)
js/script.js           nav toggle, scroll reveal, footer year
assets/images/          Blender renders
assets/video/            unused — kept for future gameplay clips if you add them
assets/resume/           unused — no resume link is currently shown on the site
```

## Current state

- **Contact** — email is `northpath.work@gmail.com`, linked as `mailto:`.
- **Resume buttons** — removed from the nav and hero. Nothing links to `assets/resume/` right now.
- **First-Person Survival Shooter Prototype** (featured project) — embeds the YouTube video at `https://youtu.be/XE4XHlgEyF4` as a responsive, lazy-loaded, no-autoplay 16:9 iframe. Its button is labeled **Project Details** and links to `https://github.com/Gungn1r-G/first-person-survival-shooter`.
- **Lunar Survival Prototype** — now a smaller "Additional Project" card with no media, just description/systems/tech, and its own **Project Details** button linking to `https://github.com/Gungn1r-G/lunar-survival-prototype`.
- **Blender section** — shows two real renders (`assets/images/blender-render-pink-lakeside.jpg`, `assets/images/blender-render-donut.jpg`), still positioned as a small, secondary section below Education.
- **GitHub** — main profile link (`github.com/Gungn1r-G`) still in the hero and Contact section.

All external links (GitHub, LinkedIn, YouTube embed, Project Details buttons) use `target="_blank"` and `rel="noopener noreferrer"` where applicable. The `mailto:` link intentionally has neither, since it opens the visitor's mail client rather than a web page.

## Adding more Blender renders

In `index.html`, find the `#blender` section and duplicate a `.blender__item` block:

```html
<div class="blender__item" role="listitem">
  <img src="assets/images/your-render.jpg" alt="Describe the render" loading="lazy">
</div>
```

Drop the image file in `assets/images/`, ideally compressed/resized (under ~300KB) so the site stays fast on mobile.

## Running locally

No build step needed — just open `index.html` in a browser, or serve the folder locally:

```bash
python3 -m http.server 8000
```

Then visit `http://localhost:8000`.

## Deploying to GitHub Pages (free)

1. Create a new GitHub repository (e.g. `portfolio`) and push this folder's contents to the `main` branch.
2. In the repo, go to **Settings → Pages**.
3. Under "Build and deployment," set **Source** to `Deploy from a branch`, branch `main`, folder `/ (root)`.
4. Save. GitHub will publish the site at `https://<your-username>.github.io/<repo-name>/`.
5. Push again any time you update content — Pages redeploys automatically.

## Notes

- Layout, color, typography, and animation are unchanged from the original design — this update only touched the items listed above.
- Animation respects `prefers-reduced-motion`.
- No forms, no backend, no analytics, no data collection.
