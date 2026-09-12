# Farheen Shaikh — Portfolio

Static portfolio site. Plain HTML/CSS, no build step, no dependencies beyond a Google Fonts stylesheet. Hosted on GitHub Pages.

Live at https://farheeeeeeen.github.io/portfolio/

## Running it locally

No build step — open `index.html` in a browser, or serve the directory:

```
python3 -m http.server 8000
```

## Structure

- `index.html` — homepage
- `project-ai-automation.html`, `project-growth.html`, `project-mvp.html`, `project-positioning.html`, `project-engagement-retention.html` — the five project pages
- `read.html` + `writing/` — writing section; `writing/_template.html` is the article template
- `resume.html` — résumé
- `images/` — screenshots and video (compress before committing; there is no optimization step)

## Deploying

Push to `main`. GitHub Pages serves from `main` / root, live about a minute later.
