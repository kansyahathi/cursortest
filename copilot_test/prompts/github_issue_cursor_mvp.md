@cursor Build an interactive static site for the XRM presentation (zero-build)

**Goal**
Create `/site` per `docs/FT_presentation_XRM.md` with 4 routes (Intro, Modules, Business Canvas, Roadmap),
load content from `/content/*.md`, add theme toggle, simple animations, print-friendly styling, and
GitHub Pages deploy workflow. Open a PR "feat(site): interactive XRM presentation".

**Scope**
- Pure HTML/CSS/JS (no bundlers). Optional pinned CDN libs.
- Hash router: `#/intro`, `#/modules`, `#/canvas`, `#/roadmap`.
- Markdown loading via fetch from `/content/*.md`.
- Basic accessibility, responsive design, print CSS.

**Acceptance Criteria**
- `site/index.html` works locally; routes render content.
- Dark/light theme persists.
- Print to PDF is clean and paginated.
- Lint passes with no critical errors.
- `.github/workflows/pages.yml` deploys to GitHub Pages.

**Notes**
If `file://` fetch is blocked locally, document:
```
python3 -m http.server 8080 -d site
```
