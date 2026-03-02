# My Portfolio

A clean, minimal academic/developer portfolio built with **Astro**, hosted on **GitHub Pages**, with content managed as **Markdown files**.

## 🚀 Quick Start

```bash
npm install
npm run dev        # http://localhost:4321
npm run build      # build to /dist
npm run preview    # preview the build
```

---

## 📁 Project Structure

```
my-portfolio/
├── .github/
│   └── workflows/
│       └── deploy.yml        # Auto-deploy to GitHub Pages on push
├── src/
│   ├── layouts/
│   │   └── Base.astro        # Shared nav/footer layout
│   ├── pages/
│   │   ├── index.astro       # Home page
│   │   ├── projects.astro    # Projects (auto-loaded from content/)
│   │   ├── publications.astro # Publications (auto-loaded from content/)
│   │   ├── cv.astro          # CV page
│   │   ├── Beyond_Academics.astro  # Beyond academics overview page
│   │   ├── Beyond_Academics/
│   │   │   └── trips.astro         # Trips photo page
│   │   └── contact.astro     # Contact page
│   ├── content/
│   │   ├── projects/         # One .md file per project
│   │   └── publications/     # One .md file per paper
│   ├── env.d.ts              # Astro env types
│   └── styles/
│       └── global.css        # All styles
├── public/
│   ├── docs/                 # PDFs (resume, papers, etc.)
│   ├── tour/
│   │   └── images1/          # Tour/trip photos
│   ├── beyond/               # Life-event photos (non-tour)
│   ├── miscellaneous/        # Miscellaneous photos
│   ├── images/               # Legacy/general image folder (optional)
│   └── favicon.svg
├── package.json
├── package-lock.json
└── astro.config.mjs
```

---

## ✏️ Customising Content

### 1. Personal info
Edit these files:
- `src/layouts/Base.astro` — your name in the nav logo and footer
- `src/pages/index.astro` — your bio, stats, and featured work
- `src/pages/cv.astro` — your education, experience, skills, awards
- `src/pages/Beyond_Academics.astro` — beyond academics overview
- `src/pages/Beyond_Academics/trips.astro` — trips and tour photos
- `src/pages/contact.astro` — your email and social links

### 2. Adding a publication
Create a new file in `src/content/publications/`:

```md
---
title: "Your Paper Title"
authors: "Your Name, Co-Author"
year: 2024
venue: "Conference / Journal Name"
description: "One paragraph describing the paper."
pdf: "/docs/your-paper.pdf"
arxiv: "https://arxiv.org/abs/XXXX.XXXXX"
code: "https://github.com/you/repo"
doi: "10.XXXX/XXXXX"
tags: ["tag1", "tag2"]
---
```

Papers are auto-listed, sorted by year. Only include the frontmatter fields you have.

### 3. Adding a project
Create a new file in `src/content/projects/`:

```md
---
title: "Project Name"
description: "What it does and why it matters."
year: 2024
featured: true          # shows in the featured grid at top
status: "active"        # active | archived | wip
github: "https://github.com/you/repo"
demo: "https://your-demo.com"
tags: ["Python", "PyTorch"]
---
```

### 4. Adding PDFs
Drop PDF files into `public/docs/` and reference them as `/docs/filename.pdf`.

### 5. Adding photos
- Trips/tours: add files to `public/tour/images1/` and reference as `/tour/images1/filename.jpg`
- Beyond academics events: add files to `public/beyond/` and reference as `/beyond/filename.jpg`
- Misc photos: add files to `public/miscellaneous/` and reference as `/miscellaneous/filename.jpg`

---

## 🌐 Deploying to GitHub Pages

1. Create a GitHub repo (e.g. `yourusername.github.io` or `portfolio`)
2. Push this project to the repo's `main` branch
3. In GitHub → Settings → Pages → set Source to **GitHub Actions**
4. The workflow at `.github/workflows/deploy.yml` will auto-build and deploy on every push
5. Update `site` in `astro.config.mjs` to match your URL:
   - For user site: `https://yourusername.github.io`
   - For project site: `https://yourusername.github.io/repo-name` (also set `base: '/repo-name/'`)

---

## 🎨 Customising Design

All styles are in `src/styles/global.css`. CSS variables at the top control the entire colour scheme:

```css
:root {
  --bg: #f5f2ec;          /* page background */
  --accent: #c84b2f;      /* links, tags, highlights */
  --text: #1a1816;        /* body text */
  ...
}
```

Fonts are loaded from Google Fonts (Instrument Serif + DM Mono + Geist).

---

## 🛠 Tech Stack

| Tool | Purpose |
|------|---------|
| [Astro](https://astro.build) | Static site generator |
| GitHub Pages | Free hosting |
| Markdown | Content authoring |
| CSS (no framework) | Styling |
| GitHub Actions | Auto-deploy CI/CD |

100% free. No database. No backend. No build complexity.
