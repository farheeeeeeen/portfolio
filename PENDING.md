# Portfolio — Pending Checklist

Everything still to finish before sharing the link with hiring managers. Grouped by priority.

_Last audited against the files on disk: 2026-08-18._

---

## 🔴 Blockers (dead links on live pages)

- [ ] **AI Automation "See the code →"** — `project-ai-automation.html:156`, still `href="#"`. Point it at the GitHub repo for the content-ops system, or delete the link. **This is the only dead link left on the site.**

---

## 🟠 Content to add / confirm

- [ ] **More writing pieces.** `read.html` currently lists one real essay (the SAFE calculator build). The External slot is empty — the obvious candidate is the dematerialisation / MCA Rule 9b explainer (65,582 organic users). Needs its live URL to wire in.
- [ ] **Iteration 1 vs Iteration 2 screenshots** for the SAFE essay. The draft originally referenced before/after screenshots that aren't in the repo; those sentences were reworded to stand on their own. If the screenshots exist, drop them in `writing/images/` and the before/after section can be restored to its stronger form.
- [ ] **Positioning annotated screenshots** — the four cards (Carta, Qapita, HR, Finance) currently show clean page screenshots. Annotating them to mark the positioning choices would make the argument visible rather than implied.
- [ ] **SAFE calculator Impact** — shows "live + ungated" with no usage numbers. Add report-download / traffic figures if available, or leave as-is (defensible for a conviction tool).
- [ ] **ROI calculator Impact** — same; the coverage stat (4/5/2) is in, usage numbers optional.
- [ ] **Remaining inline image slots** on project pages (AI system architecture diagram, the four engagement formats). Any slot without a file renders its filename in mono type, which reads as deliberate rather than broken — so these are upgrades, not blockers.

---

## 🟢 Polish / nice-to-have

- [ ] **Repo weight.** `images/safe_calculator.mp4` (8.1 MB) and `images/roi_calculator.mp4` (11 MB) are the two heaviest tracked files, ~19 MB of a small repo. Re-encode smaller (lower bitrate / shorter loop) if first-load feels slow on mobile.
- [ ] **Review every image** for sensitive EquityList data (customer names, revenue, unreleased features) — crop/blur as needed.
- [ ] **Custom domain** (optional) — e.g. farheenshaikh.com via Settings → Pages.
- [ ] **Test on mobile + a slow connection** — open every page on a phone once. This is the worst-case reader.
- [ ] **Favicon** — add a small `favicon.ico` or icon link if you want one in the browser tab.
- [ ] **Confirm GitHub Pages is enabled** — Settings → Pages → `main` / `(root)`, then load https://farheeeeeeen.github.io/portfolio/.

---

## ✅ Done

- [x] Homepage — 5 category cards, restrained design, Geist + IBM Plex Mono
- [x] All 5 hub pages built with locked copy + category accents
- [x] `resume.html` built
- [x] Positioning page — full-width expanding cards
- [x] Homepage card images in place (`ai-automation.svg`, `calculators.webp`, `growth.png`, `positioning.png`, `engagement.webp`)
- [x] Hero images — **removed site-wide by design.** Don't reintroduce them.
- [x] Calculator demo loops — `safe_calculator.mp4` + `roi_calculator.mp4` live on `project-mvp.html` (GIF originals stay local, gitignored)
- [x] Heavy source assets compressed to WebP and originals gitignored (verified untracked: the 44 MB and 28 MB GIFs, `Incorporation-Report-20260601.xlsx`)
- [x] Consistent nav — breadcrumb, sticky Home + Projects dropdown + Contact/Read/Résumé
- [x] Responsive (desktop → mobile) + reduced-motion + keyboard focus
- [x] Homepage socials wired (LinkedIn, X, GitHub)
- [x] SAFE / ROI "See it live →" point at the real `www.equitylist.co` URLs
- [x] Positioning "See them live →" placeholder removed (commit `b9e4b2a`) — it is no longer a dead link
- [x] Résumé retention label verified correct — `resume.html` says "lifted 30-day retention 36%". (The earlier note that the résumé still had 7-day/30-day swapped is out of date.)
- [x] First real writing piece published (`writing/building-a-safe-calculator-with-ai.html`); placeholder `example-piece.html` deleted and the dashed placeholder note removed from `read.html`
- [x] `writing/_template.html` nav fixed — it pointed at four project pages that never existed (`project-safe`, `project-roi`, `project-engagement`, `project-coins`)
- [x] Explainer figure settled at 65,582; "9 inbound leads" removed everywhere and not to be reintroduced
- [x] DEPLOY.md (GitHub Pages + image/video handling)
- [x] MAINTENANCE.md (how to update everything)

---

## Discreet-search reminders (keep in mind throughout)

- Repo is **public** — anyone with the link can see it, and it's findable.
- Keep **commit messages neutral** (no "job hunt", "applying", etc.).
- Nothing in **images, filenames, or copy** should signal you're actively looking.
- Don't upload `_archive/` to the public repo.
- Only `portfolio_site/` is ever published. The parent folder stays local.
