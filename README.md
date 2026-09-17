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

Open `index.html` and search for `TODO`. Each value that still needs attention is marked in an HTML comment or shown as placeholder text.

At minimum, update:

- the biography in the `#about` section;
- `YOUR_EMAIL@example.com` in the header and footer;
- `YOUR_PROFILE_ID` in both Google Scholar links;
- the research descriptions and project links;
- the publication and honors placeholders;
- the “Last updated” date in the footer when appropriate.

The GitHub links already point to `https://github.com/sieuanhta`. The canonical and Open Graph URLs already use `https://sieuanhta.github.io/`.

## Add or remove research projects

In `index.html`, find `<section id="research">`. Each project is one block beginning with:

```html
<article class="research-item">
```

Copy a complete block to add a project, or remove one complete block to delete it. Keep the project description to one to three sentences. When links are available, replace each placeholder span with an anchor, for example:

```html
<p class="item-links" aria-label="Project links">
  <a href="https://example.com/paper.pdf">Paper</a>
  <a href="https://github.com/username/repository">Code</a>
</p>
```

## Add publications

Publications are grouped by year inside `<section id="publications">`. Copy the existing `.publication-year` section for a new year, and copy the `.publication` article for each additional publication in that year.

Replace every placeholder with verified information. The supported metadata links are Paper, PDF, Code, and DOI. Use one of these status labels as appropriate: `Published`, `Accepted`, `Under Review`, or `Preprint`.

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

For honors, use the commented `.award-list` example in `index.html` and keep each entry in the format `Award — Organization/Event — Year`.

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
