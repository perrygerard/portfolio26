# piwow.co

Personal portfolio for Matt Piwowarski. One self-contained `index.html` plus its images — no build step, no dependencies, no server-side code.

## Files

| Path | What it is |
| --- | --- |
| `index.html` | The whole site: markup, styles, and scripts in one file |
| `img/` | Case-study images (WebP) |
| `media/` | Screen recordings (MP4) with WebP posters |
| `favicon.png`, `apple-touch-icon.png` | Site icons |
| `og.jpg` | Link-preview image (1200×630) |
| `.nojekyll` | Tells GitHub Pages to serve files as-is |

## Publishing with GitHub Pages

1. Create a new repository and upload everything in this folder to the repository root (`index.html` must sit at the top level, not inside a subfolder).
2. In the repository, go to **Settings → Pages**.
3. Under **Build and deployment**, set **Source** to *Deploy from a branch*, pick your default branch and the `/ (root)` folder, and save.
4. Wait a minute, then open the URL Pages shows you.

### Using piwow.co as the domain

1. In **Settings → Pages → Custom domain**, enter `piwow.co` and save. GitHub adds a `CNAME` file to the repository for you.
2. At your DNS provider, point the apex domain at GitHub's four A records, and add a `CNAME` record for `www` pointing at `<your-username>.github.io`. GitHub's Pages documentation lists the current IP addresses — use those rather than any copied from elsewhere.
3. Once DNS resolves, tick **Enforce HTTPS**.

## Before it goes live

- **Link previews.** `og:image` and `og:url` in the `<head>` are absolute URLs pointing at `https://piwow.co/`. If the site lives anywhere else, update both — relative paths don't work for social scrapers.
- **The Olli play link.** The "Play Olli" button points at a GitHub Pages site under another account. Move the build somewhere you control before sharing the portfolio widely.

## Local preview

Opening `index.html` directly works. To serve it over HTTP instead:

```
python3 -m http.server 8000
```

Then visit http://localhost:8000.
