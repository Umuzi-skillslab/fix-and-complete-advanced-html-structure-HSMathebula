# Project documentation

This document satisfies the written deliverable outline: overview, issues, fixes, layout techniques, selectors, motion design, accessibility, browsers, local viewing, and limitations.

---

## 1. Overview of the website and its purpose

**Media Production Company** is a small, static **four-page** website (Home, About, Media, Contact) built with **semantic HTML5** and **CSS**. It promotes fictional media services—**video production**, **audio**, and **editing**—and gives visitors a **media gallery** (videos, audio sample, map, testimonials) plus a **contact form** with validation.

**Goals:**

- Present services and team credibility clearly on **index** and **about**.
- Demonstrate **embedded media** (HTML `<video>`, `<audio>`, map `<iframe>`) on **media**.
- Collect enquiries through an **accessible, validated form** on **contact**.
- Meet coursework requirements: **Flexbox**, **CSS Grid**, **selector variety**, **pseudo-classes**, **transitions/transforms/animation**, and **responsive** layout.

---

## 2. Issues found: errors and missing features in the starter code

The original starter used **non-semantic** wrappers (`<div class="top">`, `<div class="nav">`, `<div class="bottom">`), **no** `<main>`, **no** `lang`, **charset**, or **viewport**, and **anonymous `<div>`** sections instead of `<section>` / `<article>` / `<figure>`.

**HTML gaps included:**

- **About:** Missing **third service**; portfolio as **raw `<img>`** without `<figure>`/`<figcaption>`; **no CSS Grid** gallery.
- **Contact:** **No labels** (placeholders only); wrong **`type="text"`** for email/phone; **no** `fieldset`/`legend`, **radio**, **select**, **date**, **checkbox**; **no** validation attributes; **no** `action`/`method` on `<form>`.
- **Media:** **One video** without **`controls`** or **fallback**; **no second video**; **no `<audio>`**; **no `iframe`**; testimonials as **bare images** without figures.
- **Home:** **No** service cards with images/captions; **no** strong hero CTA structure.

**CSS gaps included:**

- **No Flexbox** on navigation or cards; **no CSS Grid**.
- **Poor contrast** on `.hero` (`lightgray` + `#ddd` text).
- **No** pseudo-classes, **no** attribute/child/combination selectors beyond basics.
- **No** `text-shadow`, **transforms**, **transitions**, or **`@keyframes`**.
- **No** `@media` queries; **no** rules for `video`/`audio`.
- **Minimal** form styling; magic values (`blue`, loose `px`).

A **detailed line-by-line list** is in **`design/issues-identified.txt`** (and mirrors the earlier `ISSUES.txt` structure if you keep both).

---

## 3. Fixes and implementations

**Structure & semantics**

- Replaced layout divs with **`<header>`**, **`<nav><ul><li>`**, **`<main id="main">`**, **`<section class="… container">`**, **`<article class="card">`**, **`<figure>` / `<figcaption>`**, **`<footer>`**, and **`<address>`** with `mailto`/`tel` links.

**Content completeness**

- **Home:** Hero **section**, three **service cards** with images and captions, **feature** figure, **CTA** button to contact.
- **About:** **Team** figures with roles; **three** service articles; **six** portfolio items in a **responsive grid**.
- **Media:** **Two** videos (`controls`, `<source>`, text fallback, `poster`); **`<audio>`** inside a **figure**; **Google Maps `iframe`** with `title` and no inline border; **three** testimonial figures.
- **Contact:** **`action`/`method`**, **three fieldsets**, **labels** + **`for`/`id`**, types **`email`**, **`tel`**, **`date`**, **`select`**, **`radio`**, **`checkbox`**, **`textarea`**, **`submit`**; **`required`**, **`minlength`**, **`maxlength`**, **`pattern`**; **CSS Grid** layout for the form columns (personal | service + message).

**Assets**

- **SVG** placeholders under **`images/`** where JPEGs were missing; **video/audio** filenames documented under **`media/`**.

**CSS architecture**

- Split into **`css/base.css`** (reset, variables, typography), **`css/layout.css`** (container, header, footer, main), **`css/components.css`** (nav, hero, cards, grids, media, forms), imported from **`css/styles.css`**.

---

## 4. Flexbox layouts implemented

| Location | Role of Flexbox |
|----------|------------------|
| **`header.container`** | Row: site title and nav **side by side**; wraps on small screens. |
| **`nav ul`** | Row of links, **`justify-content: flex-end`**, **`align-items: center`**, **`flex-wrap`** for narrow widths. |
| **`.service-cards`** | Service **cards** in a row with **`gap`**, **`flex-wrap`**, **`justify-content: center`**. |
| **`footer.container`** | Footer contact row with **`space-between`**; stacks in **`@media`**. |
| **`footer address`** | Flex row for email/phone; column on mobile. |
| **`.team`** | Team **figures** in a wrapping row, **centred**. |
| **`.video-container`** | **Two video figures** side by side, wrapping on small viewports. |
| **`.contact-fieldset`** (personal/message columns) | **`flex-direction: column`** so the message **textarea** can grow with **`flex: 1`**. |

**Rubric alignment:** multiple **distinct** flex contexts; **`justify-content`** and **`align-items`** used more than once; **`flex-direction`** and **`flex-wrap`** both used, including responsive behaviour.

---

## 5. CSS Grid layouts implemented

| Selector | Purpose |
|----------|---------|
| **`.grid-gallery`** | **Portfolio** on About: **`grid-template-columns: repeat(auto-fit, minmax(250px, 1fr))`**, **`grid-template-rows` / `grid-auto-rows`**, **`gap`**. |
| **`.testimonial-grid`** | **Testimonials** on Media: **`auto-fit` / `minmax(220px, 1fr)`**, rows + gap. |
| **`.contact-form-columns`** | **Contact form:** **two columns** — personal fieldset **spans two rows** on the left; **service** (row 1) and **message** (row 2) on the right. **`grid-template-rows: auto 1fr`**. |

**Narrow screens (`max-width: 768px`):** contact grid becomes **one column** with explicit row order (personal → service → message).

---

## 6. Selectors and pseudo-classes added

**Selector types (examples)**

- **Element:** `body`, `h1`, `img`, `video`, `audio`, `form`, `fieldset`, `legend`, `label`.
- **Class:** `.container`, `.card`, `.btn`, `.grid-gallery`, `.contact-form-columns`, etc.
- **ID:** `#main`.
- **Descendant:** `nav ul li`, `.card figure`, `footer.container address a`.
- **Child:** `section.container > p`, `.service-cards > .card`, `fieldset > legend`.
- **Attribute:** `nav ul li a[href]`, `input[type="email"]`, `input[type="text"]`, `button[type="submit"]`, etc.

**Combination examples**

- `a.active`, `section.hero h2 + p`, `.contact-fieldset--personal`, `footer.container address p:first-of-type`.

**Pseudo-classes (examples)**

- **`:hover`** — nav links, `.btn`, `.card`, images, grid figures, submit button, footer links.
- **`:focus`** — text, email, tel, date, textarea, select.
- **`:not(:focus)`** — default border treatment on some inputs.
- **`:nth-child(2)`** — second nav item emphasis (demo pattern).
- **`:last-child`** — e.g. `.card p:last-child`.
- **`:first-of-type`** — footer address first paragraph.
- **`:not(.contact)`** — centre text on sections except contact.

---

## 7. Animations, effects, transforms, and transitions

**Text effect**

- **`text-shadow`** on **`h1`** in the dark header for readable depth.

**Keyframe animation**

- **`@keyframes fadeIn`** on **`.hero`**: opacity and slight **translateY** on load (**~2s ease-in**).

**Transforms**

- **Nav links:** **`translateY(-2px)`** on hover.
- **`.btn` / submit:** **`translateY(-3px)`** on hover.
- **Cards / gallery figures:** **`scale(1.05)`** or **`scale(1.02)`** on hover.
- **Images (cards, feature, team, grids):** **`rotate(2deg)`** on hover.

**Transitions**

- Links, buttons, cards, inputs, and images use **`transition`** on **transform**, **box-shadow**, **color**, **background**, or **border** (multiple declarations across **`components.css`**).

---

## 8. Accessibility improvements

- **`lang="en"`**, **`charset`**, **`viewport`**, and meaningful **`<title>`** / **meta description** per page.
- **Landmarks:** **`header`**, **`nav`**, **`main`**, **`footer`**, **`address`**.
- **Form:** **Visible labels** tied with **`for`/`id`**; **fieldset/legend** grouping; **HTML5 validation** to reduce bad submissions.
- **Images:** **`alt`** text on **`<img>`**; **SVG** titles where used as images.
- **Video/audio:** **`controls`**; **fallback text**; **`poster`** on videos.
- **iframe:** **`title`** describing the map; **no** redundant inline styling that hides focus outlines on custom controls (native controls used).
- **Links:** **`mailto:`** and **`tel:`** in footer for actionable contact.

---

## 9. Cross-browser compatibility and browser-specific CSS

**Testing approach**

- Build targets **modern evergreen browsers** (**Chrome**, **Edge**, **Firefox**, **Safari**). **Test in at least two** and note results in your report/screenshots.

**Techniques used**

- **Standard Flexbox and Grid** (widely supported).
- **`clamp()`** for fluid typography (supported in current browsers).
- **`:focus`** styles for keyboard users; **`:hover`** for pointer devices (touch devices may not show hover—layout does not depend on hover for usability).

**Browser-specific CSS**

- **None required.** No `-webkit-` hacks were added. If an older browser mis-renders **Grid**, the page still **degrades** to stacked blocks because **grid items** are block-level.

**Third-party content**

- **Google Maps iframe** may behave differently if cookies/blockers restrict embeds; map is an assignment requirement, not guaranteed offline.

---

## 10. How to view the website locally

1. **Clone or download** the repository.
2. Open the project folder in your editor.
3. **Option A — open files directly:** Double-click **`index.html`** (some browsers restrict **iframe** or **media** paths on **`file://`**).
4. **Option B — local server (recommended):**
   - **VS Code:** install **Live Server** and “Go Live” from the project root.
   - **Node:** from the project root run `npx --yes serve .` and open the URL shown in the terminal.
5. Place **`media/sample1.mp4`**, **`media/sample2.mp4`**, and **`media/sample-audio.mp3`** in **`media/`** if you want playback (filenames must match **`media.html`**).

---

## 11. Known issues or limitations

- **Media files:** Audio/video **will not play** until the correct files exist under **`media/`** (paths are already wired in HTML).
- **Form `action="#"`:** Suitable for a **static demo**; a real site would POST to a server script or service.
- **Map embed:** Depends on **Google** availability and network; **not** for offline-only demos.
- **SVG “photos”:** Placeholders are **vector graphics**, not photographs—replace **`src`** with real **JPG/WebP** when you have assets.
- **Assignment PDFs / wireframes:** Stored under **`design/`** (e.g. **`wireframe.pdf`**)—keep them in sync with this doc if the layout changes.

---

*Last updated to match the current repository structure (`design/issues-identified.txt`, `docs/`, `css/`, four HTML pages).*
