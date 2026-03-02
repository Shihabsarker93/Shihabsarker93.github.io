Perfect. Below is your **fully edited, production-ready README** with:

* Clear architecture explanation
* Golden workflow
* Navigation clarification
* Route casing warning
* Codex guardrail template
* Clean structure
* No redundancy
* No architectural changes

You can replace your entire README with this.

---

# My Portfolio

A clean, minimal academic/developer portfolio built with **Astro**, hosted on **GitHub Pages**, with content managed as **Markdown files**.

🔗 Live site:
[https://shihabsarker93.github.io/](https://shihabsarker93.github.io/)

---

## 🧭 Site Architecture Overview

The main experience is a **single long homepage** (`/`) with sections for:

* Home
* Projects
* Publications
* CV
* Beyond Academics
* Contact

The top navigation uses **scrollspy** to highlight the section currently in view.

The site also keeps **standalone routes**:

* `/projects`
* `/publications`
* `/cv`
* `/contact`
* `/Beyond_Academics`
* `/Beyond_Academics/trips`
* `/beyond-academics/*`

Homepage sections and standalone pages share the **same section components**, so editing content once updates everywhere.

---

# 🚀 Quick Start

```bash
npm install
npm run dev        # http://localhost:4321
npm run build      # build to /dist
npm run preview    # preview the production build
```

---

# ✅ Golden Workflow (Always Follow)

1. Make changes (usually inside `src/components/sections/*` or `src/styles/global.css`)

2. Verify locally:

```bash
npm run build
```

3. If build passes:

```bash
git add .
git commit -m "Describe change"
git push
```

If GitHub emails a build failure:

* Go to **Repo → Actions**
* Open the latest failed workflow
* Fix the issue locally and push again

---

# 📁 Project Structure

```
my-portfolio/
├── .github/
│   └── workflows/
│       └── deploy.yml
├── src/
│   ├── layouts/
│   │   └── Base.astro
│   ├── components/
│   │   └── sections/
│   │       ├── ProjectsSection.astro
│   │       ├── PublicationsSection.astro
│   │       ├── CVSection.astro
│   │       ├── ContactSection.astro
│   │       └── BeyondAcademicsSection.astro
│   ├── pages/
│   │   ├── index.astro
│   │   ├── projects.astro
│   │   ├── publications.astro
│   │   ├── cv.astro
│   │   ├── contact.astro
│   │   ├── Beyond_Academics.astro
│   │   ├── Beyond_Academics/
│   │   │   └── trips.astro
│   │   └── beyond-academics/
│   │       ├── interests.astro
│   │       ├── community.astro
│   │       ├── photos.astro
│   │       └── trips.astro
│   ├── content/
│   │   ├── projects/
│   │   └── publications/
│   └── styles/
│       └── global.css
├── public/
│   ├── docs/
│   ├── tour/images1/
│   ├── beyond/
│   ├── miscellaneous/
│   └── favicon.svg
├── package.json
├── package-lock.json
└── astro.config.mjs
```

---

# ✏️ Customising Content

## 🔹 Single Source of Truth

All main sections must be edited in:

```
src/components/sections/*
```

These are rendered by both:

* Homepage scroll (`/`)
* Standalone pages (`/projects`, `/contact`, etc.)

Do NOT duplicate markup inside page files.

---

## 🔹 Where To Edit (Cheat Sheet)

Change section content globally:

* `src/components/sections/*`

Change navbar or scrollspy:

* `src/layouts/Base.astro`

Change styling:

* `src/styles/global.css`

Add a publication:

* Create `.md` file in `src/content/publications/`

Add a project:

* Create `.md` file in `src/content/projects/`

Add PDFs:

* Place in `public/docs/`

Add photos:

* Trips → `public/tour/images1/`
* Beyond → `public/beyond/`
* Misc → `public/miscellaneous/`

---

# 🧭 Navigation Model

### Homepage (`/`)

* Nav links use anchors:

  * `/#home`
  * `/#projects`
  * `/#publications`
  * `/#cv`
  * `/#beyond-academics`
  * `/#contact`
* Scrollspy updates active nav underline via `IntersectionObserver`

### Standalone Pages

* Nav links use route paths:

  * `/projects`
  * `/publications`
  * `/cv`
  * `/contact`
  * `/Beyond_Academics`
* Active state is route-based

This dual navigation model is intentional.

---

# 🔁 Beyond Subpage Back Behavior

Subpages under:

```
/beyond-academics/*
```

Must use back links to:

```
/#beyond-academics
```

NOT `/Beyond_Academics`.

This preserves homepage scroll context.

---

# 🔒 Core Architecture Rules (Do Not Break)

### 1. Single Source of Truth

* Edit only `src/components/sections/*`
* Pages must render components, not duplicate section markup

### 2. Dual Navigation Model Must Stay Intact

* Homepage = anchor navigation + scrollspy
* Standalone pages = route navigation

### 3. Scrollspy Rules

* Only active on homepage
* Watches IDs:

  * home
  * projects
  * publications
  * cv
  * beyond-academics
  * contact
* Observer config:

  * `rootMargin: "-35% 0px -55% 0px"`
  * `threshold: 0`

### 4. Static Deployment Constraints

* Must remain fully static
* Contact form = `mailto:` only
* No backend/server assumptions

### 5. Route Compatibility Rules

* These routes must remain valid:

  * `/Beyond_Academics`
  * `/Beyond_Academics/trips`
* Lowercase routes (`/beyond-academics/*`) must not break uppercase routes

⚠ GitHub Pages is case-sensitive.
Do not rename or change route casing without updating all links.

### 6. Style Contracts

* Preserve anchor offset:

  ```css
  section[id] { scroll-margin-top: 90px; }
  ```
* Nav underline tied to `.active` / `.is-active`

---

# 🤖 Codex / AI Guardrail

Before making changes:

* Read this README
* Strictly follow **Core Architecture Rules (Do Not Break)**

Do NOT:

* Duplicate section markup
* Break shared components
* Break dual navigation model
* Remove scrollspy
* Change route compatibility
* Break static GitHub Pages behavior

### Recommended Prompt Template

```
Read README.md and strictly follow “Core Architecture Rules (Do Not Break)”.
Only implement the requested UI change.
Do not modify routing, scrollspy, or section component structure.
Run npm run build and ensure it passes.
```

---

# 🎨 Customising Design

All styles live in:

```
src/styles/global.css
```

Theme variables:

```css
:root {
  --bg: #f5f2ec;
  --accent: #c84b2f;
  --text: #1a1816;
}
```

Fonts:

* Instrument Serif
* DM Mono
* Geist

---

# 🛠 Tech Stack

| Tool           | Purpose               |
| -------------- | --------------------- |
| Astro          | Static site generator |
| GitHub Pages   | Free hosting          |
| Markdown       | Content management    |
| CSS            | Styling               |
| GitHub Actions | CI/CD                 |

100% free.
No database.
No backend.
Fully static.

---

# 🧠 Final Architecture Summary

This site intentionally supports:

* A smooth, modern single-page scroll experience
* Fully functional standalone pages
* Shared content via reusable components
* Scroll-driven navigation
* Static GitHub deployment

All section edits must happen in `src/components/sections/*` to stay consistent.



