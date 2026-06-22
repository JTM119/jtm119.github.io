# Personal Website
## Project Overview
A personal website with two main pages: an About page with work history and a Projects page with project blurbs. Built with static HTML/CSS/JS, hosted on GitHub Pages. Interactive demos are added per project over time.

## Project Structure
```
my-website/
├── index.html
├── about/
│   └── index.html
├── projects/
│   └── index.html
├── demos/
│   └── <project_name>/
│       ├── index.html
│       └── (demo-specific static files)
├── static/
│   ├── css/
│   │   ├── reset.css
│   │   ├── typography.css
│   │   └── main.css
│   └── js/
│       └── main.js
└── materials/
```

## Tech Stack
- Frontend: Vanilla HTML/CSS/JS, no frontend frameworks
- Hosting: GitHub Pages (deployed from repo root or `/docs` folder)
- No backend, no build step required
- Content is sourced from `materials/` and written directly into HTML files

## Source Materials
Work history and project information lives in the `materials/` folder. Always refer to it as the source of truth for content on the About and Projects pages.

## URL Structure
GitHub Pages serves static files. Clean URLs are achieved via folder/index.html convention:
- `/` → `index.html` (home/landing page)
- `/about/` → `about/index.html` (About page)
- `/projects/` → `projects/index.html` (Projects page)
- `/demos/<project_name>/` → `demos/<project_name>/index.html` (demo pages)

## Page Requirements

**Home page (index.html)**
- Landing page with brief intro
- Navigation to About and Projects pages

**About page (about/index.html)**
- Brief bio/intro section at the top
- Work history section populated from `materials/`
- Shared header, footer, and nav (duplicated across pages or extracted via JS include)

**Projects page (projects/index.html)**
- Card or grid layout, one entry per project
- Each card includes project name, blurb, and relevant dates or technologies from `materials/`
- Each card includes a link to `/demos/<project_name>/` for projects that have a demo

## Project Demos
Interactive demos are added per project over time. Two types are supported:

- **Frontend-only**: JS/CSS demos that run entirely in the browser. Files go in `demos/<project_name>/`. Can be rendered directly or inside an iframe embedded in the projects page.
- **Static showcases**: For demos too heavy to run live, use pre-computed examples, GIFs, or video walkthroughs embedded in the demo page.

Demo files go in:
- `demos/<project_name>/index.html`
- `demos/<project_name>/` (any additional JS, CSS, assets scoped to that demo)

## Deployment
- The site deploys via GitHub Pages from the repo root (or `/docs` folder if preferred).
- No build step is required. Push HTML/CSS/JS and changes are live automatically.
- Set a custom domain in the GitHub Pages settings and add a `CNAME` file to the repo root if using one.

## Code Standards
- All styles go in `static/css/`. No inline styles.
  - `reset.css` for baseline reset
  - `typography.css` for fonts and text styles
  - `main.css` for layout and components
- JavaScript goes in `static/js/main.js` only, unless a demo requires its own JS, in which case scope it to `demos/<project_name>/`.
- Use semantic HTML throughout (`main`, `section`, `article`, `nav`, etc.)
- Mobile-responsive using CSS only
- No dependencies or package managers unless a demo specifically requires them

## Before Making Changes
Always read the `materials/` folder before editing content-related files. If something in the materials is ambiguous, ask before assuming.