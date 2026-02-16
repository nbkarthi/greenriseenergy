# Greenrise Energy Solutions

Solar EPC company website and blog.

## Blog (Minimal Mistakes + Jekyll)

The blog uses the **Minimal Mistakes** Jekyll theme. Two Markdown posts are in `_posts/`:

- **`_posts/2026-02-16-solar-inception-india.md`** — Solar inception in India (National Solar Mission)
- **`_posts/2026-02-17-tamil-nadu-solar-journey.md`** — Tamil Nadu's solar journey

After GitHub Pages builds the site, these appear at:

- `/blog/2026/02/16/solar-inception-india/`
- `/blog/2026/02/17/tamil-nadu-solar-journey/`

**Before pushing:** In `_config.yml`, set `repository` to your GitHub repo (e.g. `username/greenriseenergy`).

## Hosting on GitHub Pages

1. Push the repo to GitHub.
2. **Settings → Pages** → Source: **Deploy from a branch** → Branch: **main** → Folder: **/ (root)**.
3. (Optional) Custom domain is set via the `CNAME` file; configure DNS as in [GitHub’s custom domain docs](https://docs.github.com/en/pages/configuring-a-custom-domain-for-your-github-pages-site).

The site is built with Jekyll (including the Minimal Mistakes theme and the two `.md` posts). Your existing static pages (e.g. `index.html`, `blog/index.html`) are kept as-is.