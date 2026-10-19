# Dr. C. Janie Chang — Academic Portfolio

Independent, static academic portfolio website for **Dr. C. Janie Chang**, Academic Executive Director of the Master of Professional Accountancy (MPAc) program at the UC Davis Graduate School of Management.

This is a personal professional portfolio inspired by the visual language of the [UC Davis GSM faculty page](https://gsm.ucdavis.edu/faculty/c-janie-chang). It is **not** an official university website.

> **Before public deployment:** content, images, and representation should be reviewed and approved by Dr. Chang.

## Tech stack

- HTML5
- CSS3 (Grid, Flexbox, custom properties)
- Vanilla JavaScript (ES6+)
- No React, Vue, Next.js, TypeScript, Tailwind, or Bootstrap

## File organization

```text
/
├── index.html              # Single-page portfolio
├── css/
│   ├── styles.css          # Design tokens, layout, components
│   ├── animations.css      # Subtle motion + reduced-motion
│   └── responsive.css      # Breakpoints (375–1440px)
├── js/
│   ├── data.js             # All structured portfolio content
│   └── main.js             # Rendering + interactions
├── assets/images/          # Local image assets
├── robots.txt
├── sitemap.xml
└── README.md
```

## Run locally

Any static file server works. Examples:

```bash
# Python
python3 -m http.server 8080

# Node (if available)
npx serve .
```

Then open `http://localhost:8080`.

Or open `index.html` directly in a browser (clipboard copy works best on `http://` / `https://` origins).

## Edit portfolio content

Almost all repeating content lives in **`js/data.js`** as `PORTFOLIO_DATA`:

| Key | Content |
|-----|---------|
| `profile` | Name, titles, contact, CV links |
| `about` / `education` | Biography and degrees |
| `appointments` | Academic experience timeline |
| `publications` | Full 43-entry CV bibliography |
| `books` / `otherScholarship` | Textbook editions and related writing |
| `teaching` | Interests, courses, expertise panels |
| `leadership` / `awards` / `service` / `grants` / `news` | Remaining sections |

Hero copy and contact markup also appear in `index.html` for SEO and no-JS readability; keep those in sync when updating profile facts.

### Add a publication

1. Open `js/data.js`.
2. Append an object to `publications` with: `id`, `title`, `authors`, `year`, `venue`, `volume`, `issue`, `pages`, `type`, `status`, `doi`, `url`, `tags`, `featured`, `citation`.
3. Only add verified DOIs/URLs.
4. Assign research `tags` only when supported by the paper’s subject.
5. Refresh the browser — filters and featured lists update automatically.

## Image assets

See [`assets/images/README.md`](assets/images/README.md).

Current local files are development copies from public faculty/publisher sources. Confirm licensing before production use. Do not add UC Davis seals/logos without authorization, and never use AI-generated likenesses.

## Deploy

### GitHub Pages

1. Push this repository to GitHub.
2. Settings → Pages → Source: Deploy from branch `main` / root (or `/docs` if you move files).
3. Update `canonical` / Open Graph URLs in `index.html`, plus `robots.txt` and `sitemap.xml`, replacing `https://example.com/`.

### Netlify

1. Connect the repository in Netlify.
2. Build command: *(none)* — publish directory: repository root.
3. Update canonical and sitemap URLs to the production domain.

## Primary sources

1. [April 2026 CV (PDF)](https://gsm.ucdavis.edu/sites/default/files/2026-04/JChangVita_2026_April_GSM.pdf)
2. [UC Davis GSM faculty profile](https://gsm.ucdavis.edu/faculty/c-janie-chang)
3. [McGraw Hill — Accounting Information Systems](https://www.mheducation.com/highered/product/Accounting-Information-Systems-Richardson.html)
4. [2026 Teacher of the Year announcement](https://gsm.ucdavis.edu/news/celebrating-our-2026-student-and-teacher-award-honorees)
5. [IJSS DOI (LAM framework paper)](https://doi.org/10.1504/IJSS.2026.153420)
6. [SSRN working paper](https://papers.ssrn.com/sol3/papers.cfm?abstract_id=6188540)

## Data notes & verification status

- **All 43 refereed CV publications** are included in `js/data.js`, transcribed from the April 2026 CV.
- **DOIs** are included only when independently verified in the project brief or publisher records. Many older entries intentionally have `doi: null`.
- **Publication #2** (Large Action Models paper): the April 2026 CV listed a forthcoming 2025 status; the site uses the verified publisher DOI record (2026, Vol. 15, Issue 3, pp. 160–178).
- **Fifth textbook edition** is labeled **forthcoming (2027)** and is not presented as published.
- **Grant total (~$75,560)** is labeled as the total of four documented **collaborative** grants—not personal or lifetime funding.
- **2017 Provost’s Innovation award** is labeled collaborative (shared initiative).
- **Gallagher Hall campus photos** are documented as optional slots and are not bundled pending authorization.
- Exact news article dates on some GSM blog posts may be approximate when the source page only provides year-level context; links point to original pages.

## Interactive features

- Sticky header, mobile menu, active section highlighting
- Smooth scrolling and scroll-to-top
- Expandable experience timeline
- Publication search, year/category filters, sorting
- Show all / show fewer publications
- Copy citation
- Accessible accordion for additional service details
- IntersectionObserver entrance animations (disabled under `prefers-reduced-motion`)

## Accessibility & SEO

- Semantic landmarks and one `h1`
- Open Graph + JSON-LD `Person` schema (verified facts only)
- Visible focus styles, keyboard-friendly navigation
- Lazy-loaded non-critical images
- Mobile-friendly viewport and no horizontal overflow intent
