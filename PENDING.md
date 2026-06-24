# Portfolio — Pending Checklist

Everything still to finish before sharing the link with hiring managers. Grouped by priority.

---

## 🔴 Blockers (site has dead links / missing pages until these are done)

- [ ] **Build `resume.html`** — the Résumé button on every page points here; it doesn't exist yet. (Ask Claude to build it from the resume copy in the Master Spec / resume draft.)
- [ ] **Add the 5 homepage card images** to `images/`:
  - `ai-automation.png`
  - `calculators.png`
  - `growth.png`
  - `positioning.png`
  - `engagement.png`
- [ ] **Add the 6 project hero images** to `images/`:
  - `ai-automation-hero.png`
  - `growth-hero.png`
  - `safe-hero.png`
  - `roi-hero.png`
  - `engagement-hero.png`
  - `coins-hero.png`
  *(Positioning uses annotated screenshots inside its cards rather than a single hero — see below.)*

---

## 🟠 Real links to fill (currently placeholder `#`)

- [ ] **X / Twitter URL** — homepage social links (`index.html`, lines ~141)
- [ ] **GitHub URL** — homepage social links (`index.html`, line ~142)
- [ ] **AI Automation "See the code →"** — point to the GitHub repo for the content-ops system (`project-ai-automation.html`)
- [ ] **Positioning "See them live →"** — point to one of the live EquityList pages, or the solutions hub (`project-positioning.html`)
- [ ] **Read button** — already points to `read.html` ✓ (no action)
- [ ] **SAFE / ROI "See it live →"** — already point to the real equitylist.co calculator URLs ✓ (verify they're correct)

---

## 🟡 Content to add / confirm

- [ ] **Confirm the 65,742 figure** against Search Console (Master Spec also shows 65,550). Used on the Growth page and the homepage Growth card — must match. Pick the verified number and update both.
- [ ] **SAFE calculator Impact** — currently shows "live + ungated" (no usage numbers). Add report-download / lead / traffic numbers if you have them, or leave as-is (legitimate for a conviction tool).
- [ ] **ROI calculator Impact** — same; coverage stat (4/5/2) is in, usage numbers optional.
- [ ] **Positioning annotated screenshots** — the four cards (Carta, Qapita, HR, Finance) each have a full-width screenshot slot. These should be the live pages **with annotations** marking the positioning choices. (Upload the 4 page screenshots → Claude can produce annotated versions.)
- [ ] **Real writing pieces** — replace the two template entries in `read.html` with real pieces. For "Read here" essays, build them from `writing/_template.html`. Delete the dashed placeholder note once done.
- [ ] **Project screenshots/illustrations inside pages** — each project page has inline `[ screenshot ]` / `[ illustration ]` slots (e.g. AI system architecture diagram, calculator progressive shots, the four engagement formats). Add real images.

---

## 🟢 Polish / nice-to-have

- [ ] **Calculator "watch it work" loops** — short silent WebP/MP4 loops for SAFE/ROI (see DEPLOY.md for how to handle video on GitHub Pages).
- [ ] **Compress every image** to 150–400 KB before committing (TinyPNG / Squoosh).
- [ ] **Review every image** for sensitive EquityList data (customer names, revenue, unreleased features) — crop/blur as needed.
- [ ] **Custom domain** (optional) — e.g. farheenshaikh.com via Settings → Pages.
- [ ] **Test on mobile** — open every page on a phone once.
- [ ] **Favicon** — add a small `favicon.ico` or icon link if you want one in the browser tab.

---

## ✅ Done

- [x] Homepage — 5 category cards, restrained design, Geist + IBM Plex Mono
- [x] All 7 project pages built with locked copy + category accents
- [x] Positioning page — full-width expanding cards
- [x] Read list page + individual article template + example
- [x] Consistent nav — breadcrumb, sticky Home + Projects dropdown + Contact/Read/Résumé
- [x] Prev/next navigation chained across all 7 projects
- [x] Responsive (desktop → mobile) + reduced-motion + keyboard focus
- [x] DEPLOY.md (GitHub Pages + image/video handling)
- [x] MAINTENANCE.md (how to update everything)

---

## Discreet-search reminders (keep in mind throughout)

- Repo is **public** — anyone with the link can see it, and it's findable.
- Keep **commit messages neutral** (no "job hunt", "applying", etc.).
- Nothing in **images, filenames, or copy** should signal you're actively looking.
- Don't upload `_archive/` to the public repo.
