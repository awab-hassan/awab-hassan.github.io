# Awab Hassan — Portfolio

A static, single-page portfolio for **Awab Hassan** — DevOps/SRE engineer and AppSec specialist. Built with plain HTML, CSS, and JavaScript (no build step). Hosted on GitHub Pages.

> Live site: **https://awab-hassan.github.io/** *(or your project-pages URL — see [Deployment](#deployment))*

---

## Stack

- **HTML5 / CSS3 / vanilla JS** — no framework, no bundler, no build step.
- Google Fonts (Orbitron, Space Grotesk, Share Tech Mono).
- Font Awesome and Boxicons via CDN.
- ScrollReveal (CDN) for entrance animations.
- Custom canvas-based particle background ("Six Eyes" effect).

## Project structure

```
.
├── index.html              # Entry point (GitHub Pages serves this by default)
├── .nojekyll               # Disables Jekyll so GH Pages serves files verbatim
├── .gitignore
├── README.md
└── assets/
    ├── css/jjk-styles.css  # All styles
    ├── js/jjk-main.js      # All scripts
    ├── img/                # Hero / portrait images
    ├── projects/           # Project thumbnails
    └── certs/              # Certificate images
```

## Local preview

No build step is required. From the project root:

```bash
# Python 3
python -m http.server 8080

# or, Node
npx serve .
```

Then open <http://localhost:8080>.

## Deployment

### Option A — User site (`<username>.github.io`)

1. Create a repo named exactly **`<your-github-username>.github.io`** (for Awab: `awab-hassan.github.io`).
2. Push this project to the **`main`** branch:
   ```bash
   git init
   git add .
   git commit -m "Initial portfolio"
   git branch -M main
   git remote add origin git@github.com:awab-hassan/awab-hassan.github.io.git
   git push -u origin main
   ```
3. In **Settings → Pages**, set **Source = Deploy from a branch**, **Branch = main**, **Folder = / (root)**.
4. Visit `https://<username>.github.io/` — the site is live in a minute or two.

### Option B — Project site (`<username>.github.io/<repo>`)

1. Push to any repo (e.g. `portfolio`).
2. In **Settings → Pages**, choose **Branch = main, Folder = / (root)**.
3. Visit `https://<username>.github.io/<repo>/`.
4. **Update `<link rel="canonical">` and the Open Graph `og:url` in `index.html`** to match this URL so SEO/social previews are correct.

> All asset paths in `index.html` are **relative** (`assets/...`), so both options work without further changes.

## Customization

- **Replace projects** — edit the `.projects__item` blocks in `index.html` (HTML comments mark where to add more).
- **Replace certificates** — drop new files into `assets/certs/` and add a matching `<a>…<li>` block in the Certificates section.
- **Replace favicon** — swap `assets/img/gojo-whoami.png` for a dedicated `favicon.ico` / `favicon.png` and update the two `<link rel="icon">` tags in the `<head>`.
- **Recolor / restyle** — edit `assets/css/jjk-styles.css`.

## Notes

- `.claude/` is gitignored — it holds local Cowork settings, not project code.
- No secrets, API keys, or credentials are stored in this repo. The only contact identifier is a public mailto: link.
- No build pipeline is needed — pushing to `main` is the entire deploy.

## License

All code in this repo is © Awab Hassan. The illustration assets in `assets/img/` and `assets/certs/` belong to their respective creators / issuers.
