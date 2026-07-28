# applair.in

Source for **[applair.in](https://applair.in)** — AppLair open software
consulting (mobile, platforms, AI tooling) and privacy policies for Android
apps published under AppLair.

- Landing page: `/`
- Machine-readable summary: `/llms.txt`
- Privacy policies: `/privacy/`
  - cape — `/privacy/cape/` · `/privacy/cape/data-safety.html`

## Stack

Plain static HTML, CSS, and a few lines of JS. No build step.
Deployed on **Cloudflare Pages** with custom domain `applair.in`.

## Local preview

```sh
python3 -m http.server 8000
# or
npx wrangler pages dev .
```

Then visit <http://localhost:8000/>.

Note: `_headers` and `_redirects` are applied by Cloudflare Pages at the
edge and will **not** take effect under `python -m http.server`.
Use `npx wrangler pages dev .` if you want to exercise them locally.

## Deployment — Cloudflare Pages

The site is served by Cloudflare Pages from this repository's `main` branch.

Project settings:

- **Project name:** `applair`
- **Production branch:** `main`
- **Framework preset:** None
- **Build command:** _(none — static site)_  or `npx wrangler deploy`
- **Build output directory:** `.`

Configuration files:

- `wrangler.jsonc` — Wrangler config (static asset directory).
- `_headers` — security headers (HSTS, CSP, X-Frame-Options) + cache rules.
- `_redirects` — clean-URL rules and legacy path fallbacks.
- `404.html` — branded not-found page.

### First-time Cloudflare Pages setup

1. Cloudflare Dashboard → **Workers & Pages** → **Create application** → **Pages** → **Connect to Git**.
2. Authorize GitHub access to `nitishagar/applair` (after repo rename) and select it.
3. Framework preset: None. Build command: empty. Output directory: `.`.
4. Save and deploy. The site is reachable at `https://applair.pages.dev`.

### Custom domain

1. In the Pages project → **Custom domains** → **Set up a domain**.
2. Enter `applair.in` (and repeat for `www.applair.in`).
3. Because the zone is on Cloudflare, DNS is configured automatically.
   TLS certificates are provisioned within a minute or two.

### Contact addresses (Cloudflare Email Routing)

The landing page links to three `@applair.in` addresses. Set them up once
via Cloudflare → **Email** → **Email Routing** for the `applair.in` zone:

| Address | Forwards to |
|---|---|
| `hello@applair.in` | _(your personal inbox)_ |
| `projects@applair.in` | _(your personal inbox)_ |
| `privacy@applair.in` | _(your personal inbox)_ |

Cloudflare Email Routing provisions MX/TXT/SPF records automatically.

## Migration notes (historical)

This repository was originally `nitishagar/privacy` — a Jekyll site served by
GitHub Pages at `nitishagar.github.io/privacy/`. It was repurposed to host
the AppLair consulting presence at `applair.in`, with existing privacy
policies moved under `/privacy/…`.

Cutover order for the Play Store privacy URL (important):

1. Deploy this repo to Cloudflare Pages at `applair.in`.
2. Verify `https://applair.in/privacy/cape/` renders.
3. Update the cape Play Store listing privacy URL to `https://applair.in/privacy/cape/`.
4. Rename the GitHub repo `nitishagar/privacy` → `nitishagar/applair`.
5. Update the local remote: `git remote set-url origin git@github.com:nitishagar/applair.git`
   (adjust for your ssh alias).
6. Disable GitHub Pages on the repo after traffic has settled.

## License

© AppLair. Site content all rights reserved. Privacy policies are
informational and specific to the named apps.
