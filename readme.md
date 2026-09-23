# Portfolio

Personal static HTML portfolio for Layne Fester's business IT work and learning projects.

Live domain: https://www.laynefester.me

## Pages

- `/` — introduction and internship interests
- `/projects/` — project hub
- `/ehlert-recovery/` — email migration and website recovery
- `/homelab/` — Active Directory and security logging lab
- `/camera-nas/` — manual NAS backups and camera installation
- `/resume/` — public Experience overview; URL retained for existing links
- `/contact/` — university email, LinkedIn and GitHub

## Local preview

From the site root, run `python -m http.server 8765 --bind 127.0.0.1` and open
http://127.0.0.1:8765. No build step or package installation is required.
Use a local server rather than opening the HTML files directly; links use site-root paths.

## Public content

The application résumé is private and is not stored in this repository.
The lab diagram is conceptual and contains no private addresses or account names.
The homepage portrait is served from `assets/layne-fester-portrait.png`; the `CNAME` domain configuration is retained.

## License

No license / personal project.
