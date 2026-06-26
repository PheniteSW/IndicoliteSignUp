# Indicolite — Sign Up

Beta waitlist landing page for **Indicolite**, a browser-based 2D game creation studio.
Build 2D games from any browser — no downloads, no installs, no high-powered PC.

- **Beta site:** https://indicolite.onrender.com/
- **Company:** https://polypall.github.io/Phenite/
- **Feedback:** polySW@proton.me

## What's here

| File | Purpose |
|------|---------|
| `index.html` | The full single-page waitlist site (HTML + CSS + JS inline). |
| `assets/icon.png` | App icon / favicon / logo. **Add this file** (see below). |
| `assets/icon.svg` | Placeholder logo used automatically until `icon.png` exists. |

## Add the real app icon

The page references `assets/icon.png` for the favicon, the header logo, and the
social share image. A generated SVG placeholder is shown until you add it.

To use your icon, drop the PNG at `assets/icon.png` (a square image, e.g. 512×512,
works best). No code changes needed — it's already wired up.

> Note: the original image link (`i.postimg.cc`) could not be fetched from the
> build environment because that host is blocked by the network egress policy.
> Add the PNG directly to the repo, or host it on an allowed domain.

## Wire up real email capture

By default the form saves sign-ups to `localStorage` so the page is testable.
To collect emails for real, open `index.html`, find `FORM_ENDPOINT`, and set it
to your form backend — e.g. a [Formspree](https://formspree.io) endpoint or your
own API. The form POSTs `{ "email": "..." }` as JSON.

## Run locally

It's a static site — just open `index.html`, or serve the folder:

```bash
python3 -m http.server 8000
# then visit http://localhost:8000
```

## Deploy to GitHub Pages

This is a static site (no build step), so GitHub Pages serves it directly from
the repo root.

1. Push this branch and merge it into `main` (Pages deploys from a branch).
2. In the repo: **Settings → Pages**.
3. Under **Build and deployment**, set **Source = Deploy from a branch**.
4. Choose **Branch = `main`**, **Folder = `/ (root)`**, then **Save**.
5. Wait ~1 minute. The site goes live at
   `https://polypall.github.io/IndicoliteSignUp/`.

Notes:
- `.nojekyll` is included so GitHub serves the files as-is (no Jekyll processing).
- All asset paths are **relative** (`assets/icon.png`), which is required because
  project Pages are served from a subpath. Don't switch them to leading-slash
  absolute paths or they'll 404.

Other static hosts (Render static site, Netlify, etc.) also work — point them at
the repo root; `index.html` is the entry point.
