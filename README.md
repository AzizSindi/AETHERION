# AETHERION

A single-page site for **AETHERION** — a productised vision of **Digital Healthcare Engineering (DHE)**: lifetime digital healthcare for ships and offshore structures through continuous monitoring, accurate diagnosis, and timely intervention.

The page is **fully self-contained**. `index.html` has all CSS, JavaScript, and the hero image (embedded as a base64 data URI) inlined into the single file, so it works both as a local file you can double-click and as a GitHub Pages site with zero build step.

## Files

| File | Purpose |
|---|---|
| `index.html` | The entire site — open it directly in a browser, or deploy as-is. |
| `assets/hero-ship-dhe.jpg` | Standalone copy of the hero image. Used for the social-share (Open Graph) preview, and available if you'd prefer to link the image externally (see below). |
| `.nojekyll` | Tells GitHub Pages to serve the files as-is and skip Jekyll processing. |

## Deploy to GitHub Pages

1. Create a new repository on GitHub (e.g. `aetherion`).
2. Add these files to the repo root and push:
   ```bash
   git init
   git add .
   git commit -m "AETHERION site"
   git branch -M main
   git remote add origin https://github.com/<your-username>/<your-repo>.git
   git push -u origin main
   ```
3. In the repo, go to **Settings → Pages**.
4. Under **Build and deployment → Source**, choose **Deploy from a branch**.
5. Select branch **`main`** and folder **`/ (root)`**, then **Save**.
6. Wait ~1 minute. Your site will be live at:
   `https://<your-username>.github.io/<your-repo>/`

> For a site at `https://<your-username>.github.io/` (no sub-path), name the repository exactly `<your-username>.github.io`.

## Customising

- **Contact email** — the footer and any contact links use the placeholder `hello@aetherion.example`. Find-and-replace it with your real address.
- **Brand name** — every visible label reads **AETHERION**. If you want a different spelling, find-and-replace `AETHERION` (and the lowercase `aetherion` in the email) across `index.html`.
- **Social-share image URL** — the `og:image` / `twitter:image` meta tags point to `assets/hero-ship-dhe.jpg` as a relative path. Once deployed, for the richest link previews on some platforms you can switch these to the absolute URL, e.g. `https://<your-username>.github.io/<your-repo>/assets/hero-ship-dhe.jpg`.

### Optional: lighter HTML by linking the image externally

The embedded base64 image makes `index.html` large (~300 KB). If you'd rather keep the HTML small, the standalone image is already in `assets/`. Replace the inline data URI with a normal relative `src`:

1. In `index.html`, find the hero `<img>` tag (its `src` starts with `data:image/jpeg;base64,…`).
2. Replace the entire long `src="data:image/jpeg;base64,…"` value with:
   ```html
   src="assets/hero-ship-dhe.jpg"
   ```

The page will look identical; the browser will load the image from the `assets/` folder instead of from inside the HTML. (The trade-off: `index.html` is no longer a single self-contained file.)

## Credit

Built on the Digital Healthcare Engineering framework developed at UCL. Reference material:

- ICSOS 2021 — Sindi, Thomas & Paik: <https://discovery.ucl.ac.uk/id/eprint/10212690>
- Data-Centric Engineering review (2024): <https://doi.org/10.1017/dce.2024.14>
- Researcher profile: <https://profiles.ucl.ac.uk/81227-abdulaziz-faisal-sindi-sindi/about>
