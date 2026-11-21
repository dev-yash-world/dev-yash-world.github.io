# yashtripathi.in

Personal portfolio of Yash Tripathi. Plain static site (HTML + CSS, no build step), hosted free on GitHub Pages with the custom domain `yashtripathi.in`.

## Files

| File | Purpose |
|---|---|
| `index.html` | The whole site |
| `favicon.svg` | Browser tab icon |
| `CNAME` | Tells GitHub Pages to serve the site on `yashtripathi.in` |
| `.nojekyll` | Stops GitHub from running Jekyll (this is what printed raw `---` front matter on the old site) |
| `robots.txt`, `sitemap.xml` | Search engine basics |

## One-time setup

1. Create a public repo on GitHub, for example `yashtripathi.in` or `<username>.github.io`.
2. Push these files:
   ```bash
   git init
   git add .
   git commit -m "New portfolio"
   git branch -M main
   git remote add origin https://github.com/<username>/<repo>.git
   git push -u origin main
   ```
3. In the repo: **Settings > Pages > Build and deployment**, Source = *Deploy from a branch*, Branch = `main`, folder `/ (root)`.
4. Same page, **Custom domain** = `yashtripathi.in`, save. Tick **Enforce HTTPS** once the certificate is ready (can take up to an hour).
5. At your domain registrar, set DNS:

   | Type | Host | Value |
   |---|---|---|
   | A | @ | 185.199.108.153 |
   | A | @ | 185.199.109.153 |
   | A | @ | 185.199.110.153 |
   | A | @ | 185.199.111.153 |
   | CNAME | www | `<username>.github.io` |

   Remove any old A/CNAME records that point to your current host.
6. Optional but recommended: **Settings > Pages > Verify domain** so nobody else can claim it.

## Updating the site

Edit `index.html`, commit, push. GitHub Pages redeploys in about a minute.

To add a project, copy one `<li>` inside the right `<ul class="stops">` block in the Work section. To show it on the map too, add a `<circle class="st">` and `<text>` on that line's path in the hero SVG.

## Preview locally

```bash
python3 -m http.server 8000
# open http://localhost:8000
```
