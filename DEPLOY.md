# Portfolio — Deploy & Maintain

Static site, no build step. Deploys to GitHub Pages as-is.

---

## 1. Repo structure

```
your-repo/
├── index.html                  ← homepage
├── read.html                   ← writing list
├── resume.html                 ← (to build)
├── project-ai-automation.html
├── project-growth.html
├── project-safe.html
├── project-roi.html
├── project-positioning.html
├── project-engagement.html
├── project-coins.html
├── images/                     ← all screenshots go here
│   ├── ai-automation.png       (homepage card)
│   ├── ai-automation-hero.png  (project page hero)
│   ├── calculators.png         (homepage card)
│   ├── safe-hero.png
│   ├── roi-hero.png
│   ├── growth.png  / growth-hero.png
│   ├── positioning.png / positioning-hero.png
│   ├── engagement.png / engagement-hero.png
│   └── coins.png / coins-hero.png
├── writing/                    ← native "Read here" pieces (optional, as you add them)
└── .nojekyll                   ← empty file (see step 5)
```

The HTML refers to images by these exact filenames. Match them and images appear; until then each slot shows the filename as a placeholder (by design — nothing looks broken).

---

## 2. Put it on GitHub Pages

1. Create a **public** repo (e.g. `farheen-portfolio`).
2. Upload all the files (drag-and-drop in the GitHub web UI is fine, or `git push`).
3. Repo → **Settings** → **Pages**.
4. Under "Build and deployment", Source = **Deploy from a branch**; Branch = **main**, folder = **/ (root)**. Save.
5. Wait ~1 min. Your site is live at `https://<username>.github.io/<repo-name>/`.
6. That `…github.io/…` URL is what you share with hiring managers.

(Optional, later: a custom domain like `farheenshaikh.com` can point at Pages via Settings → Pages → Custom domain.)

---

## 3. Screenshots — handle these carefully

**Compress before committing.** Raw screenshots are 1–3 MB; that makes the site slow and bloats the repo.
- Run each through **TinyPNG** (tinypng.com) or **Squoosh** (squoosh.app) → aim for 150–400 KB.
- Target width ~1600px max; nobody needs more on a card or hero.

**Review every image for the discreet search:**
- Crop or blur internal data, customer names, revenue figures, unreleased features in any EquityList product screenshot.
- Nothing in the image — or its filename, or your commit messages — should signal you're job-hunting.

**Aspect ratios:** keep card images similar (≈16:10) so the homepage grid lines up. Heroes can be wider (≈16:9 or 2:1).

---

## 4. Videos — do NOT commit to the repo

GitHub limits: 100 MB per file (hard), ~1 GB repo (soft). Video breaks both and slows every clone. GitHub Pages is the wrong host for video.

Options, best first for your case:
- **Short silent loops (the calculator "watch it work" sequences):** export as optimized **WebP** or MP4 loop, keep under ~2–3 MB, and these *can* live in `images/`. A loop usually reads better than a full video anyway.
- **Longer / narrated walkthroughs:** upload to **Vimeo** with privacy set to *hide from Vimeo / unlisted* (cleaner than YouTube for a quiet search), then embed the player.
- **Cloudinary** (free tier) if you want auto-optimized hosting with a direct link.

To embed a hosted video later, drop this where a screenshot slot is:
```html
<video src="images/safe-loop.webp" autoplay loop muted playsinline
       style="width:100%;height:100%;object-fit:cover"></video>
```
(For Vimeo, paste their iframe embed code instead.)

---

## 5. The `.nojekyll` file

GitHub Pages runs Jekyll by default, which ignores files/folders starting with `_`. To be safe (and to keep the `_archive/` folder from causing surprises), add an **empty file named `.nojekyll`** at the repo root. It disables Jekyll so every file serves as-is.

Don't upload the `_archive/` folder to the public repo at all — it holds the old design version and isn't needed live.

---

## 6. Before you share the link — checklist

- [ ] All five card screenshots + seven hero images added and compressed
- [ ] No sensitive/internal data visible in any image
- [ ] `Read` button → real pieces added to `read.html` (or hide the button if not ready)
- [ ] `resume.html` built and the Résumé button works
- [ ] Real blog/X/LinkedIn/GitHub URLs filled in (search for `href="#"` and replace)
- [ ] `28.shaikh.farheen@gmail.com` is the email you want public
- [ ] The "See it live / See the code" links on project pages point to the right URLs
- [ ] Confirm the 65,742 figure against Search Console (used on Growth page + homepage)
- [ ] Open every page once on desktop and once on a phone
- [ ] `.nojekyll` added; `_archive/` not uploaded

---

## 7. To swap the font later

In every HTML file, the top of `:root` has `--display` and `--body` set to Geist. Change both lines to another loaded family and the whole site reflows. (You'd also update the Google Fonts `<link>` in each `<head>`.)
