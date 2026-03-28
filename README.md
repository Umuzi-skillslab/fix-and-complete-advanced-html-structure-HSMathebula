[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/uFImwIHI)
[![Open in Visual Studio Code](https://classroom.github.com/assets/open-in-vscode-2e0aaae1b6195c2367325f4f02e2d04e9abb55f0b24a779b69b11b9e10269abc.svg)](https://classroom.github.com/online_ide?assignment_repo_id=23178871&assignment_repo_type=AssignmentRepo)

## 1. Project overview and purpose

**Media Production Company** is a static **four-page** website (Home, About, Media, Contact) built with **semantic HTML5** and **CSS**. It promotes fictional **video**, **audio**, and **editing** services; the **Media** page showcases **videos**, an **audio** sample, a **map** (`iframe`), and **testimonials**; **Contact** provides a **validated form**.

**Goals**

- Present services and team credibility on **index** and **about**.
- Demonstrate **embedded media** (`<video>`, `<audio>`, map `<iframe>`) on **media**.
- Collect enquiries via an **accessible** form on **contact**.
- Satisfy coursework: **Flexbox**, **CSS Grid**, **selector variety**, **pseudo-classes**, **transitions / transforms / animation**, and **responsive** layout.

## 2. Author

- **Student:** Sipho Mathebula  
- **Repository:** GitHub Classroom assignment (see buttons above).

## 3. What this project includes

- **Pages:** `index.html`, `about.html`, `media.html`, `contact.html`
- **Styles:** `css/styles.css` imports `base.css`, `layout.css`, `components.css`
- **Assets:** `images/` (SVG placeholders), `media/` (**`sample-audio.wav`** included; **`sample1.mp4`** / **`sample2.mp4`** included if present in your clone)
- **Extra docs:** `design/issues-identified.txt`, `docs/wireframes.md`, `docs/screenshots/README.md`, `design/wireframe.pdf`

**This README** is the single project write-up (overview, issues, fixes, flex/grid, selectors, motion, accessibility, browsers, local viewing, limitations).

## 4. Requirements coverage (checklist)

| Area | Status |
|------|--------|
| HTML — 7+ semantic elements per page × 4 | Yes (`header`, `nav`, `main`, `section`, `article`, `figure`, `figcaption`, `footer`, `address`, `form`, `fieldset`, etc.) |
| 2+ videos, `controls`, fallback text | `media.html` — two `<video>` with `<source>` + text fallback |
| 1+ audio, `controls`, fallback | `media.html` — `<audio>` in `<figure>` + fallback; source **`sample-audio.wav`** |
| 1+ iframe | Google Maps embed on `media.html` (`title`, `allowfullscreen`, `.map-embed` in CSS) |
| 6+ images with `figure` + `figcaption` | Home, About, Media exceed this |
| Form — 7+ types, labels, 3+ validation | Contact: text, email, tel, date, select, radio, checkbox, textarea, submit; `required`, `minlength`, `maxlength`, `pattern` |
| CSS flexbox (2+ layouts, justify, align, direction, wrap) | Nav, cards, footer, team, videos, header, fieldsets, etc. |
| CSS Grid + `auto-fit` / `minmax` + rows + gap | `.grid-gallery`, `.testimonial-grid`, `.contact-form-columns` |
| Selectors, pseudo-classes, combinations | See §9 and comments in `css/components.css`, `layout.css` |
| Text effect, 3+ transforms, 2+ transitions, 1+ keyframes | `text-shadow` on `h1`; scale / translate / rotate; `fadeIn` on `.hero` |
| Responsive media query | `@media (max-width: 768px)` in `components.css` |

## 5. Issues found in the starter code

The original starter used **non-semantic** wrappers (`<div class="top">`, `<div class="nav">`, `<div class="bottom">`), **no** `<main>`, **no** `lang`, **charset**, or **viewport**, and generic **`<div>`** blocks instead of `<section>` / `<article>` / `<figure>`.

**HTML gaps (summary)**

- **About:** Missing **third service**; portfolio as **raw `<img>`** without `<figure>`/`<figcaption>`; **no CSS Grid** gallery.
- **Contact:** **No labels**; **`type="text"`** for email/phone; **no** `fieldset`/`legend`, **radio**, **select**, **date**, **checkbox**; **no** validation; **no** `action`/`method`.
- **Media:** One **video** without **`controls`** / **fallback**; **no second video**; **no `<audio>`**; **no `iframe`**; testimonials as **bare `<img>`**.
- **Home:** **No** service cards with images/captions; weak hero CTA.

**CSS gaps (summary)**

- **No Flexbox** on nav/cards; **no Grid**; **poor contrast** on `.hero` (`lightgray` + `#ddd`); **no** pseudo-classes or advanced selectors; **no** text-shadow, transforms, transitions, keyframes; **no** `@media`; **no** `video`/`audio` rules; minimal form styling.

A **line-by-line list** is in **`design/issues-identified.txt`**.

## 6. Fixes and implementations

**Structure:** `<header>`, `<nav><ul><li>`, `<main id="main">`, `<section class="… container">`, `<article class="card">`, `<figure>`/`<figcaption>`, `<footer>`, `<address>` with `mailto`/`tel`.

**Content:** Home — hero, three service cards, feature figure, CTA. About — team figures, three services, six portfolio grid items. Media — two videos, audio figure, map iframe, three testimonials. Contact — fieldsets, labels, typed inputs, validation, **CSS Grid** form layout (personal | service + message).

**Assets:** SVG placeholders in **`images/`**; media files under **`media/`**.

**CSS:** Split into **`base.css`**, **`layout.css`**, **`components.css`** imported from **`styles.css`**.

## 7. Flexbox layouts implemented

| Location | Role |
|----------|------|
| **`header.container`** | Title and nav **side by side**; wraps on small screens. |
| **`nav ul`** | Links in a row: **`justify-content: flex-end`**, **`align-items: center`**, **`flex-wrap`**. |
| **`.service-cards`** | Cards with **`gap`**, **`flex-wrap`**, **`justify-content: center`**. |
| **`footer.container`** | Footer row **`space-between`**; stacks in **`@media`**. |
| **`footer address`** | Email/phone row; column on mobile. |
| **`.team`** | Team figures wrapping, centred. |
| **`.video-container`** | Two video figures side by side; stacks on narrow viewports. |
| **`.contact-fieldset`** | **`flex-direction: column`** so the message **textarea** can grow (**`flex: 1`**). |

## 8. CSS Grid layouts implemented

| Selector | Purpose |
|----------|---------|
| **`.grid-gallery`** | About portfolio: **`repeat(auto-fit, minmax(250px, 1fr))`**, **`grid-template-rows` / `grid-auto-rows`**, **`gap`**. |
| **`.testimonial-grid`** | Media testimonials: **`auto-fit` / `minmax(220px, 1fr)`**, rows + gap. |
| **`.contact-form-columns`** | Contact: two columns — personal **spans two rows**; service (row 1) + message (row 2). **`grid-template-rows: auto 1fr`**. |

At **`max-width: 768px`**, the contact form becomes **one column** (personal → service → message).

## 9. Selectors and pseudo-classes

**Types (examples):** element (`body`, `h1`, `img`), class (`.container`, `.card`), ID (`#main`), descendant (`nav ul li`), child (`section.container > p`, `.service-cards > .card`), attribute (`input[type="email"]`, `a[href]`).

**Combinations (examples):** `a.active`, `section.hero h2 + p`, `footer.container address a:hover`.

**Pseudo-classes (examples):** `:hover` (links, buttons, cards, images), `:focus` (inputs), `:not(:focus)`, `:nth-child(2)`, `:last-child`, `:first-of-type`, `:not(.contact)` on sections for text alignment.

## 10. Animations, effects, transforms, and transitions

- **Text:** **`text-shadow`** on **`h1`** (header).
- **Keyframes:** **`@keyframes fadeIn`** on **`.hero`** (~2s, opacity + **`translateY`**).
- **Transforms:** **`translateY`** on nav links and buttons; **`scale`** on cards/gallery figures; **`rotate`** on images on hover.
- **Transitions:** on links, buttons, cards, inputs, images (**transform**, **box-shadow**, **color**, **background**, **border** in **`components.css`**).

## 11. Accessibility improvements

- **`lang="en"`**, **`charset`**, **`viewport`**, per-page **`<title>`** and **meta description**.
- Landmarks: **`header`**, **`nav`**, **`main`**, **`footer`**, **`address`**.
- Form: **labels** + **`for`/`id`**, **fieldset/legend**, **HTML5 validation**.
- Images: **`alt`** text; SVGs used as **`img`** include descriptive **`alt`** / SVG **`<title>`** where used.
- **Video/audio:** **`controls`**, fallback text, **`poster`** on videos.
- **iframe:** descriptive **`title`** for the map.
- Footer: **`mailto:`** and **`tel:`** links.

## 12. Cross-browser compatibility

- Targets **modern browsers** (Chrome, Edge, Firefox, Safari). **Test in at least two** and keep notes/screenshots.
- Uses **standard Flexbox and Grid**; **`clamp()`** for fluid type.
- **No vendor-only CSS** was required (`-webkit-` hacks not used).
- **`:hover`** is enhancement only; layout does not depend on it for core use.
- **Google Maps** may be affected by blockers or **offline** use.

## 13. File structure

```
├── about.html
├── contact.html
├── index.html
├── media.html
├── README.md          ← this file (full documentation)
├── design/
│   ├── issues-identified.txt
│   └── wireframe.pdf
├── css/
│   ├── base.css
│   ├── components.css
│   ├── layout.css
│   └── styles.css
├── docs/
│   ├── wireframes.md
│   └── screenshots/
│       └── README.md
├── images/            ← SVG placeholders (+ optional real images)
├── media/             ← sample-audio.wav, sample1.mp4, sample2.mp4 (as provided)
└── screenshots/       ← optional captures for your report
```

## 14. How to view the website locally

1. Clone or download the repository.
2. **Recommended:** run a **local server** (some browsers limit **`file://`** for iframe/media):
   - **VS Code:** **Live Server** → “Go Live” from the project root.
   - **Node:** `npx --yes serve .` then open the printed URL.
3. Alternatively open **`index.html`** directly if your environment allows full media/map behaviour.

## 15. Browser testing (complete for your submission)

Test **at least two** browsers (e.g. Chrome + Firefox):

- [ ] All four pages load; navigation works.
- [ ] Videos play if **`sample1.mp4`** / **`sample2.mp4`** are present.
- [ ] Audio plays (**`sample-audio.wav`**).
- [ ] Form validation blocks empty/invalid submit.
- [ ] Layout is usable at ~**375px** width.

Record results in your report; add screenshots under **`docs/screenshots/`** or **`screenshots/`** as required.

## 16. Validation (complete for your submission)

- [ ] **HTML:** [W3C Markup Validator](https://validator.w3.org/) — aim for **zero errors**.
- [ ] **CSS:** [W3C CSS Validator](https://jigsaw.w3.org/css-validator/) — validate bundled CSS as your course requires.

## 17. Related documentation files

| File | Purpose |
|------|---------|
| `design/issues-identified.txt` | Detailed starter issues ↔ fixes (line-by-line) |
| `docs/wireframes.md` | ASCII wireframes for four pages |
| `docs/screenshots/README.md` | Suggested screenshot list for markers |

## 18. Credits and references

- Fonts: system UI stack (`Segoe UI`, system-ui, sans-serif).
- Map: Google Maps embed (third-party).
- SVG placeholders: project-specific stand-ins for photos.

## 19. Submission checklist

- [ ] Media files present where referenced (`media/`).
- [ ] HTML + CSS validated (0 errors goal).
- [ ] Two browsers tested (notes + screenshots).
- [ ] Wireframes, issues log, README, screenshots per brief.
- [ ] Git commit and push to Classroom before the deadline.

## 20. Known issues and limitations

- **Videos** require **`sample1.mp4`** and **`sample2.mp4`** in **`media/`** (paths in **`media.html`**). **Audio** uses included **`sample-audio.wav`** unless you change the markup.
- **Form `action="#"`** is for a **static demo**; production would POST to a server.
- **Map iframe** needs **network** and may fail if Google or embeds are blocked.
- **SVG “photos”** are not photographs—swap **`src`** for **JPG/WebP** when you have real assets.
- Keep **`design/wireframe.pdf`** aligned with the live layout if you change structure.

---
