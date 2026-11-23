# nahid.exe — personal page

One static page (`index.html`) + one photo (`assets/nahid.jpg`). No build step, no dependencies.

## Preview locally

```bash
cd site
python3 -m http.server 8000
# open http://localhost:8000
```

## Free hosting (pick one)

### GitHub Pages (recommended — your existing setup, free 24/7)

1. Create a repo, e.g. `nahid-site` (or drop these files in the root of your existing `nahidsarker771.github.io` repo).
2. Push:
   ```bash
   cd site
   git init -b main
   git add .
   git commit -m "personal vibe-coding page"
   git remote add origin https://github.com/nahidsarker771/nahid-site.git
   git push -u origin main
   ```
3. Repo → Settings → Pages → Source: `Deploy from a branch` → `main` / `/ (root)` → Save.
4. Live at `https://nahidsarker771.github.io/nahid-site/` in about a minute (HTTPS is automatic).

If you publish inside your `nahidsarker771.github.io` repo instead, it lands at `https://nahidsarker771.github.io/` and becomes your main hub.

### Vercel (free Hobby tier, no card)

```bash
npx vercel
```
Answer the prompts (project name → `nahid`), then `npx vercel --prod`. You get `https://nahid.vercel.app` with HTTPS.

### Netlify drop (fastest, no git)

Drag the `site` folder onto https://app.netlify.com/drop — done.

## Before you publish

- Swap `assets/nahid.jpg` if you want a different photo (keep the same filename).
- Update the canonical/OG URLs in `index.html` if the final domain is not `nahidsarker771.github.io`.
