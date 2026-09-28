# Portfolio

Static HTML portfolio for Layne Fester: small-business IT work and a personal security logging lab.

Live site: https://www.laynefester.me

## Pages

- `/`: introduction and internship goal
- `/projects/`: project overview
- `/ehlert-recovery/`: email migration and website recovery
- `/homelab/`: Active Directory and security logging lab
- `/camera-nas/`: NAS backups and camera installation
- `/resume/`: résumé (nav label "Résumé")
- `/contact/`: email, LinkedIn, and GitHub

## Structure

- `assets/site.css`: all shared styles (colors, layout, light/dark mode)
- `assets/layne-fester-portrait.webp` / `.jpg`: homepage photo
- `assets/security-plus-badge.webp` / `.png`: Security+ badge (links to Credly verification)
- `assets/Layne-Fester-Resume.pdf`: downloadable résumé
- `assets/homelab-overview.svg`: lab diagram (no private addresses or account names)
- `CNAME`: custom domain for GitHub Pages
- `404.html`: custom not-found page (GitHub Pages serves it automatically)
- `robots.txt`, `sitemap.xml`: search engine hints
- `.well-known/security.txt`: where to report security issues
- `.nojekyll`: tells GitHub Pages not to run Jekyll, so `.well-known/` gets published

## Security

The site has no JavaScript, forms, or third-party requests. Each page sets a strict
Content-Security-Policy and a referrer policy with `<meta>` tags, external links open in a new tab with
`rel="noopener noreferrer"`, and the email address is HTML-entity-encoded to slow down
basic scrapers.

GitHub Pages can't send custom HTTP headers. After moving DNS to Cloudflare (proxied),
add these response headers with a Transform Rule:

- `Strict-Transport-Security: max-age=31536000; includeSubDomains`
- `Content-Security-Policy: default-src 'self'; img-src 'self' data:; style-src 'self'; script-src 'none'; object-src 'none'; base-uri 'self'; form-action 'none'; frame-ancestors 'none'; upgrade-insecure-requests`
- `X-Content-Type-Options: nosniff`
- `Referrer-Policy: strict-origin-when-cross-origin`
- `Permissions-Policy: camera=(), microphone=(), geolocation=(), interest-cohort=()`

Then the CSP `<meta>` tag can be removed (the header version also covers `frame-ancestors`).

## Local preview

From the site root run `python -m http.server 8765` and open http://127.0.0.1:8765.
Links use root paths (`/projects/`), so opening the files directly won't work.
When editing, keep styles in `assets/site.css`; inline `style=` attributes and `<script>` are blocked by the CSP.

`assets/Layne-Fester-Resume.pdf` is the public web copy of the résumé (no phone number, UWM email).
