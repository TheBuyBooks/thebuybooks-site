# TheBuyBooks — website (launch version)

Static site: wholesale account applications + special orders by email.

## Files
- `index.html` — the whole site
- `logo-mark.png` (header), `logo-full.png` (footer), `logo-icon.png`, `apple-touch-icon.png` — logos
- `CNAME` — custom domain for GitHub Pages (thebuybooks.com)

## Publish on GitHub Pages
1. Create a repository (public), e.g. `thebuybooks-site`.
2. Upload every file in this folder to the repository root.
3. Settings → Pages → Source: "Deploy from a branch" → Branch: `main`, folder `/ (root)` → Save.
4. Settings → Pages → Custom domain: `thebuybooks.com` → Save. Tick "Enforce HTTPS" once it is available.

## Cloudflare DNS (thebuybooks.com)
In Cloudflare → DNS, add:

| Type  | Name  | Value                     | Proxy       |
|-------|-------|---------------------------|-------------|
| A     | @     | 185.199.108.153           | DNS only    |
| A     | @     | 185.199.109.153           | DNS only    |
| A     | @     | 185.199.110.153           | DNS only    |
| A     | @     | 185.199.111.153           | DNS only    |
| CNAME | www   | <username>.github.io      | DNS only    |

Replace `<username>` with your GitHub username. Keep "DNS only" (grey cloud) until
GitHub finishes issuing the HTTPS certificate; you can switch the proxy on afterwards.
Do not enable Cloudflare Email Routing and Google Workspace at the same time — MX records conflict.

## Edit later
Change the text in `index.html` and commit; GitHub Pages redeploys in about a minute.

## Email addresses used on the site
- wholesale@thebuybooks.com — account applications
- orders@thebuybooks.com — special-order lists, general questions
