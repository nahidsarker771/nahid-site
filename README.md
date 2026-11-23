# nahid.exe — personal page

One static page (`index.html`) + one photo (`assets/nahid.jpg`). No build step, no dependencies.

## Live

| Host | URL |
| --- | --- |
| GitHub Pages (primary) | https://nahidsarker771.github.io/nahid-site/ |
| raw.githack mirror (preview only, rate-limited) | https://raw.githack.com/nahidsarker771/nahid-site/main/index.html |
| Repository | https://github.com/nahidsarker771/nahid-site |

Every deploy target serves this exact repo, so there is only one copy to maintain.

## One-click deploys (need your login on that service)

The repo already contains `vercel.json` and `netlify.toml`, so no settings are needed.

- **Vercel** (free Hobby): https://vercel.com/new/clone?repository-url=https://github.com/nahidsarker771/nahid-site
- **Netlify** (free): https://app.netlify.com/start/deploy?repository=https://github.com/nahidsarker771/nahid-site
- **Cloudflare Pages** (free): https://dash.cloudflare.com/?to=/:account/workers-and-pages/create → Connect to Git → pick `nahid-site` → framework preset **None**, build command empty, output directory `/`
- **Render** (free static site): https://render.com/deploy?repo=https://github.com/nahidsarker771/nahid-site
- **GitLab Pages**: import the repo at https://gitlab.com/projects/new#import_project , then add the CI job below.

Each service gives you its own subdomain (`*.vercel.app`, `*.netlify.app`, `*.pages.dev`, `*.onrender.com`), all free and HTTPS.

## CLI deploys

```bash
# Vercel — first run logs you in through the browser
npx vercel --prod

# Netlify — same, browser login on first run
npx netlify-cli deploy --prod --dir .

# Cloudflare Pages
npx wrangler pages deploy . --project-name nahid-site
```

## GitLab Pages job (`.gitlab-ci.yml`)

```yaml
pages:
  script:
    - mkdir -p public && cp -r ./* public/
  artifacts:
    paths: [public]
```

## Preview locally

```bash
python3 -m http.server 8000
# open http://localhost:8000
```

## Updating the live site

```bash
git add -A && git commit -m "update" && git push
```

GitHub Pages rebuilds in about a minute; Vercel/Netlify/Cloudflare redeploy automatically once connected.

## Before you publish elsewhere

- Swap `assets/nahid.jpg` if you want a different photo (keep the filename).
- Update the canonical/OG URLs in `index.html` if your main domain stops being `nahidsarker771.github.io/nahid-site/`.
