# Repo Index

This repo is a Hugo Blox "Academic CV" starter. It is mostly configured through Markdown/YAML content files rather than custom template code, which makes it a good template to personalize without digging deeply into Hugo internals.

## How This Site Is Put Together

- `content/` controls pages and homepage sections.
- `data/authors/me.yaml` holds the main person/profile data used across the site.
- `assets/media/` holds images such as the profile photo and logos.
- `static/uploads/` holds downloadable files such as the resume PDF.
- `config/_default/` holds site-wide Hugo and Hugo Blox configuration.
- `layouts/` is where custom template overrides would live.

Right now, this repo has only one small local layout override:

- `layouts/_partials/hooks/head-end/github-button.html`

Everything else is coming from Hugo Blox modules configured in `config/_default/module.yaml`.

## Files You Will Probably Edit First

### Identity and branding

- `config/_default/hugo.yaml`
  - Set `baseURL`
  - Set the global `title`
- `config/_default/params.yaml`
  - Set the site name under `hugoblox.identity.name`
  - Update description, theme mode, colors, typography, header, footer, SEO, analytics
- `data/authors/me.yaml`
  - Replace the sample person with your own bio, role, links, education, experience, skills, languages, and awards
- `assets/media/authors/me.png`
  - Replace the profile photo
- `static/uploads/resume.pdf`
  - Replace the sample resume

### Homepage

- `content/_index.md`
  - This is the homepage
  - It is built from blocks/sections
  - Current sections are:
    - biography/hero
    - research intro markdown
    - featured publications
    - recent publications
    - talks
    - blog/news
    - a demo CTA block that only shows on the Hugo Blox demo site

If you want a different homepage structure, this is the main file to change.

### Navigation

- `config/_default/menus.yaml`
  - Controls the main nav items:
    - Bio
    - Papers
    - Talks
    - News
    - Experience
    - Projects
    - Courses

### Secondary pages

- `content/experience.md`
  - Builds the experience page from the `me.yaml` profile data
- `content/publications/_index.md`
  - Section page for publications
- `content/projects/_index.md`
  - Projects listing page
- `content/blog/_index.md`
  - Blog listing page
- `content/courses/_index.md`
  - Courses listing page
- `content/events/_index.md`
  - Events/talks listing page

## Content You Will Likely Replace or Delete

These are sample/demo entries from the starter template:

- `content/blog/`
  - Sample posts like `get-started`, `project-management`, `second-brain`, `teach-courses`, `data-visualization`, `notebook-onboarding`
- `content/projects/`
  - Sample project cards: `pandas`, `pytorch`, `scikit`
- `content/events/example/`
  - Sample event/talk
- `content/slides/example/`
  - Sample slide deck
- `content/courses/hugo-blox/`
  - Hugo Blox course/docs content bundled as example material

If you want a cleaner personal site quickly, these are the first folders to trim.

## Route-to-File Map

- `/` -> `content/_index.md`
- `/experience/` -> `content/experience.md`
- `/blog/` -> `content/blog/_index.md` plus entries in `content/blog/*/`
- `/projects/` -> `content/projects/_index.md` plus entries in `content/projects/*/`
- `/events/` -> `content/events/_index.md` plus entries in `content/events/*/`
- `/courses/` -> `content/courses/_index.md` plus entries in `content/courses/*/`
- `/publications/` -> `content/publications/_index.md` plus publication entries you add later
- `/slides/` -> `content/slides/*/`

## Config Files

- `config/_default/hugo.yaml`
  - Core Hugo settings
  - `baseURL`
  - pagination
  - taxonomies
  - output formats
- `config/_default/params.yaml`
  - Hugo Blox site behavior and design system
  - branding
  - theme
  - typography
  - header/footer
  - search
  - comments
  - analytics
  - repository links
- `config/_default/menus.yaml`
  - Navigation menu
- `config/_default/languages.yaml`
  - Language config
- `config/_default/module.yaml`
  - Hugo module imports and mount points

## Assets and Data

- `assets/media/slides-logo.svg`
  - Logo asset used by the sample slides content
- `assets/media/authors/me.png`
  - Main profile image
- `data/authors/me.yaml`
  - Main structured person record

## Build and Deployment

- `package.json`
  - `pnpm run dev` -> `hugo server --disableFastRender`
  - `pnpm run build` -> Hugo build plus Pagefind search index generation
- `hugoblox.yaml`
  - Declares the template ID and target Hugo version (`0.161.1`)
- `netlify.toml`
  - Netlify build pipeline
- `.github/workflows/`
  - GitHub Actions for build, deploy, upgrades, and publication import

## Customization Order I Recommend

1. Replace `data/authors/me.yaml`, `assets/media/authors/me.png`, and `static/uploads/resume.pdf`.
2. Update `config/_default/hugo.yaml` and `config/_default/params.yaml` with your site name, URL, description, and theme preferences.
3. Rewrite `content/_index.md` so the homepage reflects you instead of the starter.
4. Remove sample folders from `content/blog/`, `content/projects/`, `content/events/`, `content/slides/`, and `content/courses/hugo-blox/` as needed.
5. Update `config/_default/menus.yaml` so the nav matches the pages you actually want.
6. Add your real content: projects, posts, talks, publications.

## Notes From This Initial Scan

- This template is content-driven, not code-heavy.
- There is almost no local custom layout code to untangle.
- The current repo still contains the stock sample persona and demo content.
- The local environment I checked has `hugo` installed, but not `pnpm`.
- The repo targets Hugo `0.161.1` in `hugoblox.yaml`, while the installed local Hugo is older (`0.136.5`).

That means personalization can start immediately, but a fully clean local build should use the newer Hugo version expected by the template.
