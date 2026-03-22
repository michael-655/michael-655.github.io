# CLAUDE.md

## Project Overview

Personal GitHub Pages site (`michael-655.github.io`). Currently a minimal test platform serving static HTML via Jekyll.

## Repository Structure

```
.
├── .github/workflows/jekyll-gh-pages.yml   # CI/CD: Jekyll build & GitHub Pages deploy
├── README.md                                # Site content (static HTML, not markdown)
└── CLAUDE.md                                # This file
```

- No `_config.yml` — uses Jekyll/GitHub Pages defaults.
- No `package.json`, `Gemfile`, or external dependencies.
- No linting, formatting, or testing tools configured.

## Tech Stack

- **Static site generator**: Jekyll (via GitHub Pages preinstalled dependencies)
- **Content format**: Raw HTML in `README.md`
- **Hosting**: GitHub Pages

## Build & Deployment

Deployment is automated via `.github/workflows/jekyll-gh-pages.yml`:

1. Triggered on pushes to `main` branch (or manual dispatch)
2. Jekyll builds the site from `./` into `./_site`
3. Artifact is uploaded and deployed to GitHub Pages
4. Only one deployment runs at a time (concurrency control)

There is no local build step required. To preview locally, install Jekyll and run `jekyll serve`.

## Branch Strategy

- `main` — production branch; pushes trigger deployment
- Feature branches for changes, merged into `main`

## Key Conventions

- The site content lives in `README.md` as raw HTML (not markdown)
- No package manager or dependency installation needed
- Keep the repository minimal — avoid adding unnecessary files
- All new pages/content should follow the existing HTML pattern unless migrating to markdown

## Common Tasks

| Task | Command |
|------|---------|
| Preview locally | `jekyll serve` (requires Ruby + Jekyll installed) |
| Deploy | Push to `main` branch |
| Manual deploy | Trigger workflow from GitHub Actions tab |
