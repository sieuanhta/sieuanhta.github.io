# Tien Trinh — Academic Homepage

A minimal, responsive academic homepage built with plain HTML and CSS. It has no build step, framework, runtime dependency, or JavaScript.

## Project structure

```text
.
├── index.html          # Page content and metadata
├── styles.css          # Layout, typography, mobile, and print styles
├── cv.pdf              # Replace with the current CV, keeping this filename
├── assets/
│   └── favicon.svg     # Placeholder monogram favicon
├── README.md
└── .gitignore
```

## Edit personal information

The page content is based on the current `cv.pdf`. Open `index.html` to edit the biography, research summaries, publications, awards, and contact links.

The remaining TODO is to add a verified Google Scholar profile URL when one is available. When the CV changes, also review:

- the biography and current affiliations;
- research descriptions and manuscript statuses;
- publication metadata and links;
- honors and awards;
- the “Last updated” date in the footer when appropriate.

The GitHub, LinkedIn, email, canonical, and Open Graph values are already populated.

## Add or remove research projects

In `index.html`, find `<section id="research">`. Each project is one block beginning with:

```html
<article class="research-item">
```

Copy a complete block to add a project, or remove one complete block to delete it. Keep the project description to one to three sentences. When links are available, add anchors to `.item-links`, for example:

```html
<p class="item-links" aria-label="Project links">
  <a href="https://example.com/paper.pdf">Paper</a>
  <a href="https://github.com/username/repository">Code</a>
</p>
```

## Add publications

Publications are grouped by current status or year inside `<section id="publications">`. Copy an existing `.publication-year` section for a new group, and copy a `.publication` article for each additional publication in that group.

Use only verified information. The supported metadata links are Paper, PDF, Code, and DOI. Status labels can include `Published`, `Accepted`, `Under Review`, `Preprint`, or `In Preparation`.

Example metadata:

```html
<p class="publication-meta">
  <span class="status">Preprint</span>
  <a href="https://example.com/paper">Paper</a>
  <a href="https://example.com/paper.pdf">PDF</a>
  <a href="https://github.com/username/repository">Code</a>
  <a href="https://doi.org/10.xxxx/xxxxx">DOI</a>
</p>
```

For honors, copy an existing `.award-list li` entry and keep the format `Award — Organization/Event — Year`.

## Replace the CV

Replace `cv.pdf` in the repository root with the current CV and keep the filename exactly `cv.pdf`. All site links use `/cv.pdf`, which is the correct root-relative path for the `sieuanhta.github.io` user site.

Before committing, open `http://localhost:8000/cv.pdf` during local testing to confirm the new file loads.

## Test locally

No installation or build is needed. From the repository root, start any static file server. With Python 3:

```bash
python -m http.server 8000
```

Then open `http://localhost:8000/` in a browser. Check both a wide desktop window and a narrow mobile viewport. Root-relative links such as `/cv.pdf` work correctly when served from `localhost`; opening `index.html` directly with a `file://` URL is not recommended.

## Deploy with GitHub Pages

1. Create a public GitHub repository named exactly `sieuanhta.github.io`.
2. Commit these files on the `main` branch and push them to that repository.
3. On GitHub, open **Settings → Pages**.
4. Under **Build and deployment**, set **Source** to **Deploy from a branch**.
5. Select the `main` branch and the `/(root)` folder, then click **Save**.
6. After GitHub finishes publishing, visit `https://sieuanhta.github.io/`.

GitHub Pages may take a few minutes to publish the first deployment. Future pushes to `main` will redeploy the site automatically.
