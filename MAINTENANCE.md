# Portfolio — Maintenance Guide

How to update and extend the site. No build step, no framework — plain HTML/CSS with a tiny bit of vanilla JS. You edit a file, save, push, and GitHub Pages serves it.

---

## The mental model

- **One file = one page.** `index.html` is the homepage; each `project-*.html` is a project; `read.html` lists writing; `writing/*.html` are individual articles; `resume.html` is the résumé.
- **No shared header/footer file.** Each page carries its own nav and styles inline. This is deliberate — it keeps the site dependency-free and easy to host, but it means **a nav change has to be made in every file** (see "Changing the nav everywhere" below).
- **Colour, type, and spacing live in `:root`** at the top of each file's `<style>`. Same tokens in every file.

---

## Common edits

### Fix a typo / change copy
Open the page, find the text, edit it, save. That's it.

### Change a metric or stat
Project pages: find the `.impact .grid` block near the bottom of the `<article>`. Each stat is:
```html
<div class="cell"><div class="v">2.6k → 9.3k</div><div class="k">ORGANIC CLICKS / MO</div></div>
```
`.v` is the number, `.k` is the label. Keep labels short and uppercase.

### Add a screenshot
Drop the image in `images/` with the **exact filename the page expects** (see the list in DEPLOY.md or in the `<img src="...">` tag). Compress first (TinyPNG/Squoosh, 150–400 KB). Until a file exists, the slot shows its filename as a placeholder — that's intentional.

### Fill in a real link (currently placeholder `#`)
Search each file for `href="#"` and replace with the real URL. The known placeholders are listed in PENDING.md.

---

## Adding a writing piece ("Read here")

1. In `writing/`, copy `_template.html` → rename to a slug, e.g. `positioning-is-proof.html`.
2. Fill everything in `[ square brackets ]`: title, meta line, standfirst, body.
   - `<h2>` / `<h3>` for headings
   - `<blockquote>…<cite>…</cite></blockquote>` for a pull-quote (cite optional)
   - `<figure>` blocks for images — drop files in `writing/images/`, set the `src`
   - Delete any optional block (quote, figure, list) you don't use
3. In `read.html`, copy a "Read here" entry block and point its `href` at your new file:
```html
<a class="entry" href="writing/positioning-is-proof.html">
  <div class="topline">
    <span class="kind here">Read here</span>
    <span class="src">Essay · 2026</span>
  </div>
  <h2>Your title</h2>
  <p>Your one-line blurb.</p>
  <span class="go">Read →</span>
</a>
```
4. Delete the dashed "Replace the templates…" note in `read.html` once you have real entries.

### Highlighting an external piece (ran elsewhere)
In `read.html`, copy the **External** entry block, set the `href` to the live URL (keep `target="_blank"`), and change the source label and "Read on … ↗" text.

---

## Adding a new project

1. Copy an existing single-project page (e.g. `project-growth.html`) → `project-yourname.html`.
2. Change, in order: `<title>`, meta description, the `--accent` / `--accent-bg` / `--accent-deep` trio in `:root`, the breadcrumb, the eyebrow, the `<h1>`, the meta line, the hero `<img src>`, the Problem/What I Built/Impact copy, and the bottom prev/next links.
3. Add it to the **Projects dropdown** in every page's nav (see below), and add a card on `index.html`.
4. Add its screenshots to `images/`.

The five category accents in use:
- AI Automation — teal `#0F6E56`
- Growth — blue `#185FA5`
- SAFE + ROI (Product MVPs) — coral `#993C1D`
- Positioning — plum `#534AB7`
- Engagement + Coins — sand `#854F0B`

---

## Changing the nav everywhere

Because each page is self-contained, the sticky nav (the `<nav class="mininav">` block) and the Projects dropdown menu are **duplicated in every file**. If you add/rename/remove a project, update the `.dd .menu` list in all of these:
`index.html` uses its own top buttons; every `project-*.html`, `read.html`, and `writing/_template.html` carry the dropdown.

Tip: make the change in one file, then copy the whole `<div class="menu">…</div>` block into the others. Or do a find-and-replace across files in your editor.

---

## Changing the font

In every file's `:root`, `--display` and `--body` are set to Geist. To switch:
1. Change both variables to the new family name.
2. Update the Google Fonts `<link>` in that file's `<head>` to load the new family.
Do it in all files (or find-and-replace).

---

## Deploying changes

Once it's on GitHub Pages (see DEPLOY.md), every push to the `main` branch auto-publishes in ~1 minute. Workflow:
1. Edit files locally (or in GitHub's web editor).
2. Commit + push to `main`.
3. Wait ~1 min, hard-refresh the live URL (Cmd/Ctrl+Shift+R).

**Keep commit messages neutral** — the repo is public and tied to a discreet search. "Update copy," "add screenshots," "fix link" are fine. Avoid anything that signals job-hunting.

---

## File map

```
index.html                  homepage (5 category cards)
read.html                   writing list
resume.html                 résumé (TO BUILD)
project-ai-automation.html  ┐
project-growth.html         │
project-safe.html           │ seven project pages
project-roi.html            │ (standard template, except
project-positioning.html    │  positioning = expanding grid)
project-engagement.html     │
project-coins.html          ┘
writing/
  _template.html            article template (copy per piece)
  example-piece.html        sample (linked from read.html)
  README.txt                how-to
  images/                   article images (create as needed)
images/                     all screenshots + card/hero images
  README.txt                filename list
_archive/                   old design version (DO NOT upload to public repo)
DEPLOY.md                   GitHub Pages setup + image/video handling
PENDING.md                  what's left to finish
MAINTENANCE.md              this file
.nojekyll                   keeps GitHub Pages serving files as-is
```
