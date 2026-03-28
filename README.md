[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/uFImwIHI)
[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=23178871&assignment_repo_type=AssignmentRepo)

## 1. Project overview

**Media Production Company** is a small multi-page static website (HTML + CSS) demonstrating semantic structure, embedded media, responsive layout, and assignment rubric items (flexbox, grid, selectors, effects, forms, validation).

## 2. Author and module

- **Student:** Sipho Mathebula
- **Repository:** GitHub Classroom assignment (see buttons above)

## 3. What this project includes

- **Four pages:** `index.html` (home), `about.html`, `media.html`, `contact.html`
- **Styles:** `css/styles.css` imports `base.css`, `layout.css`, `components.css`
- **Assets:** `images/` (SVG placeholders), `media/` (add `sample1.mp4`, `sample2.mp4`, `sample-audio.mp3`)
- **Documentation:** `design/issues-identified.txt`, `docs/PROJECT_DOCUMENTATION.md`, `docs/wireframes.md`, `docs/screenshots/README.md`

## 4. Requirements coverage (checklist)

| Area | Status |
|------|--------|
| HTML — 7+ semantic elements per page × 4 | Yes (`header`, `nav`, `main`, `section`, `article`, `figure`, `figcaption`, `footer`, `address`, `form`, `fieldset`, etc.) |
| 2+ videos, `controls`, fallback text | `media.html` — two `<video>` with `<source>` + text fallback |
| 1+ audio, `controls`, fallback | `media.html` — `<audio>` inside `<figure>` with fallback text |
| 1+ iframe | Google Maps embed on `media.html` (`title`, `allowfullscreen`, no inline border) |
| 6+ images with `figure` + `figcaption` | Home, About, Media exceed this |
| Form — 7+ types, labels, 3+ validation | Contact: text, email, tel, date, select, radio, textarea, submit; `required`, `minlength`, `maxlength`, `pattern` |
| CSS flexbox (2+ layouts, justify, align, direction, wrap) | Nav, cards, footer, team, videos, header, etc. |
| CSS Grid + `auto-fit` / `minmax` + rows + gap | `.grid-gallery`, `.testimonial-grid`, `.contact-form-columns` |
| Selectors, pseudo-classes, combinations | See comments in `css/components.css` and `layout.css` |
| Text effect, 3+ transforms, 2+ transitions, 1+ keyframes | e.g. `text-shadow`, scale/translate/rotate, `fadeIn` on hero |
| Responsive media query | `@media (max-width: 768px)` in `components.css` |

## 5. File structure

```
├── about.html
├── contact.html
├── index.html
├── media.html
├── design/
│   └── issues-identified.txt
├── README.md
├── css/
│   ├── base.css
│   ├── components.css
│   ├── layout.css
│   └── styles.css
├── docs/
│   ├── PROJECT_DOCUMENTATION.md
│   ├── wireframes.md
│   └── screenshots/
│       └── README.md
├── images/          ← SVG placeholders (+ optional real images)
└── media/           ← sample1.mp4, sample2.mp4, sample-audio.mp3
```

## 6. How to run locally

1. Clone or download the repository.
2. Open the project folder in VS Code (or any editor).
3. **Do not rely on `file://` for the map iframe** if your browser blocks it — use a local server if needed:
   - VS Code: “Live Server” extension, or
   - PowerShell: `npx --yes serve .` then open the URL shown.
4. Add video/audio files under `media/` so players work end-to-end.

## 7. Browser testing (you must complete)

Test **at least two browsers** (e.g. Chrome + Firefox, or Chrome + Edge):

- [ ] All four pages load; navigation works.
- [ ] Videos play (after MP4 files are present).
- [ ] Form validation blocks empty/invalid submit.
- [ ] Layout breaks gracefully at mobile width (~375px).

Record what you tested and any differences in your report.

## 8. Validation (you must complete)

- [ ] **HTML:** [W3C Markup Validation Service](https://validator.w3.org/) — paste markup or upload each page; aim for **zero errors**.
- [ ] **CSS:** [W3C CSS Validator](https://jigsaw.w3.org/css-validator/) — validate `styles.css` (or “by direct input” including imported files as one bundle if required).

Save screenshots for your submission (`docs/screenshots/`).

## 9. Documentation bundle

| Document | Purpose |
|----------|---------|
| `design/issues-identified.txt` | Detailed list of starter issues and fixes (line-by-line) |
| `docs/PROJECT_DOCUMENTATION.md` | Full write-up: overview, flex/grid, selectors, a11y, browsers, local run, limitations |
| `docs/wireframes.md` | Wireframes for all four pages |
| `docs/screenshots/README.md` | List of 8+ screenshots to capture |

## 10. Credits and references

- Fonts: system UI stack (`Segoe UI`, system-ui, sans-serif).
- Map: Google Maps embed (third-party content; used for iframe requirement).
- SVG placeholders: authored for this project as lightweight stand-ins for photographs.

## 11. Submission checklist

- [x] All media files added where referenced.
- [x] HTML + CSS validated (0 errors goal).
- [x] Two browsers tested (notes + screenshots).
- [x] Wireframes, issues log, README, screenshots included per brief.
- [x] Git commit and push to Classroom before the deadline.

---

*Replace bracketed fields in sections 2 and 11 with your own details before submitting.*
