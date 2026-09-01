# Personal site — Adelmo Brunelli

A single static page. No build step, no dependencies, no framework. `index.html` contains all the markup and CSS; the only external request is the Google Fonts stylesheet.

```
.
├── index.html
├── README.md
└── assets/
    └── Adelmo-Brunelli-CV.pdf
```

## Publishing it

Your GitHub username is `squarcia`, so the simplest option is a user site: it gets served at `https://squarcia.github.io` with no extra configuration.

1. On GitHub, create a new **public** repository named exactly `squarcia.github.io`. Leave it empty — no README, no .gitignore.
2. In a terminal, from the folder containing these files:

```bash
git init
git add .
git commit -m "Personal site"
git branch -M main
git remote add origin https://github.com/squarcia/squarcia.github.io.git
git push -u origin main
```

3. In the repository, go to **Settings → Pages**. Under *Build and deployment*, set **Source** to `Deploy from a branch`, branch `main`, folder `/ (root)`. Save.
4. Wait two or three minutes. The site appears at `https://squarcia.github.io`.

If you would rather keep the repo under a different name (say `portfolio`), everything above works the same, but the URL becomes `https://squarcia.github.io/portfolio/` and the repo must still be public unless you have GitHub Pro.

## Updating it

Edit `index.html`, then:

```bash
git add .
git commit -m "Update experience section"
git push
```

The live site refreshes within a minute or two. To preview locally before pushing, open `index.html` directly in a browser, or run `python3 -m http.server` in this folder and visit `http://localhost:8000`.

## Replacing the CV

Overwrite `assets/Adelmo-Brunelli-CV.pdf` with the new file, keeping the same filename, and push. The download links pick it up automatically.

## Adding a custom domain

If you buy a domain later, create a file named `CNAME` in the repo root containing only the domain (e.g. `adelmobrunelli.com`), point a CNAME DNS record at `squarcia.github.io`, and enable HTTPS in Settings → Pages.
