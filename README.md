# sws-ws — Sahara Wellness Spa website

Static one-page site for https://saharawellnessspa.com, served by GitHub Pages.

## Files
- `index.html` — the whole site (HTML + inline CSS, no build step)
- `CNAME` — custom domain for GitHub Pages
- `.nojekyll` — serve files as-is

## Deploy
1. Repo → Settings → Pages → Source: **Deploy from a branch**, Branch: `main` / root.
2. Custom domain: `saharawellnessspa.com`, then tick **Enforce HTTPS** once the certificate is issued.

## Cloudflare DNS (saharawellnessspa.com)
Remove the old Hostinger A/AAAA/CNAME records for `@` and `www`, then add:

| Type  | Name | Content                     | Proxy     |
|-------|------|-----------------------------|-----------|
| A     | @    | 185.199.108.153             | DNS only  |
| A     | @    | 185.199.109.153             | DNS only  |
| A     | @    | 185.199.110.153             | DNS only  |
| A     | @    | 185.199.111.153             | DNS only  |
| CNAME | www  | `<github-username>.github.io` | DNS only  |

Leave the Proton Mail records (MX, SPF/TXT, DKIM CNAMEs, DMARC) untouched.
Proxying can be switched on in Cloudflare after GitHub issues the HTTPS certificate (SSL mode: Full).

## Later
- Swap the "Call to Book" buttons for the Booker link when booking goes live.
- Replace Unsplash photos with real spa photos in `assets/`.
