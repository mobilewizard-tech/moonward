# Moonward — studio website

A static marketing site for an independent mobile app studio. Plain HTML, CSS and a few lines of vanilla JS — no framework, no build step.

## Files

```
index.html     Homepage (hero, app portfolio, how we work, traction, partners CTA)
styles.css     All styles; theme tokens live in :root at the top
script.js      Mobile menu, footer year, scroll fade-ins (site works without it)
privacy.html   Privacy policy placeholder
terms.html     Terms of use placeholder
404.html       Not-found page (Cloudflare Pages serves it automatically)
favicon.svg    Site icon
_headers       Cloudflare Pages security + caching headers
robots.txt
```

## Run locally

Open `index.html` in a browser, or serve the folder:

```bash
npx serve .
# or
python3 -m http.server 8000
```

## Customize

- **Studio name / email** — search for `Moonward` and `moonward.studio` across the files.
- **Apps** — each app is one `<a class="app-card">` block in `index.html`. Edit the name, category, blurb and platforms, and point `href` at the App Store / Google Play page. Icon colors are the `--icon-bg` / `--icon-fg` values on `.app-icon`.
- **Traction numbers** — replace the bracketed placeholders (`[00]M+`, etc.) in the `#traction` section.
- **Accent color** — change `--accent` and `--accent-glow` at the top of `styles.css`.
- **Legal pages** — replace the bracketed text in `privacy.html` and `terms.html` with your real policies (both stores require a privacy policy URL per app).

## Deploy to Cloudflare Pages

1. Push this folder to a GitHub repository:
   ```bash
   git init
   git add .
   git commit -m "Initial site"
   git branch -M main
   git remote add origin https://github.com/<you>/<repo>.git
   git push -u origin main
   ```
2. In the Cloudflare dashboard, go to **Workers & Pages → Create → Pages → Connect to Git** and pick the repository.
3. Build settings:
   - Framework preset: **None**
   - Build command: *(leave empty)*
   - Build output directory: **`/`**
4. Deploy. Every push to `main` redeploys automatically.
5. Optional: add your domain under the project's **Custom domains** tab.
