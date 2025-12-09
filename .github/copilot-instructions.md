<!-- Copilot / AI agent instructions for VictorGChen.github.io -->
# Repo overview

This repository is a small Jekyll-based GitHub Pages site (personal portfolio / CV). Key facts:

- Site engine: Jekyll (built on GitHub Pages via the `github-pages` gem).
- Local build: uses Bundler + `jekyll` (see `Gemfile`).
- Content organization: site pages live in `_pages/`, reusable bits in `_includes/`, overall structure in `_layouts/`, projects in `_projects/`, and site data in `_data/`.

# Quick local workflow

- Install gems: `bundle install` (requires Ruby & Bundler).
- Serve locally: `bundle exec jekyll serve` (site served at `http://localhost:4000`).
- Build only: `bundle exec jekyll build` (output goes to `_site/`).

If Ruby is not available locally, prefer making small changes and relying on GitHub Pages for CI builds.

# Architecture & patterns (what to know)

- Layouts: `_layouts/default.html` wraps all pages and includes `header.liquid` which builds navigation.
  - Navigation is computed in `_includes/header.liquid` by iterating `site.pages` and checking front matter keys `nav` and `nav_order`.
  - To add a nav item, add a page to `_pages/` and set `nav: true` and `nav_order: <int>` in its front matter.
- Pages: Markdown files under `_pages/` include YAML front matter (example: `_pages/about.md`). Default front matter values are set in `_config.yml` under `defaults`.
- Projects: stored in `_projects/` and defined as a Jekyll collection in `_config.yml`. Project URLs follow `/projects/:name/`.
- Data files: `_data/cv.yml` and `_data/resume.yml` hold structured content used by templates (edit those for data-driven updates).
- Assets: styles are in `assets/css/custom.css` and referenced via `{{ '/assets/css/custom.css' | relative_url }}` — use `relative_url` for paths.

# Conventions you must follow

- Front matter keys used by templates: `title`, `layout`, `permalink`, `nav`, `nav_order`, plus page-specific ones like `profile`, `subtitle`, `news` (see `_pages/*.md` for examples).
- Keep `_pages/` for top-level site pages (about, cv, projects). Use `_projects/` for project items so collection templates render them correctly.
- Do not change `baseurl` in `_config.yml` for this user site (it is intentionally empty for `username.github.io`).
- Prefer editing templates under `_layouts/` and `_includes/` when making structural changes — content belongs in `_pages/`, `_projects/`, or `_data/`.

# Integration and deployment notes

- Deployment target: GitHub Pages (main branch). The `github-pages` gem in `Gemfile` pins versions used by GitHub Pages.
- Avoid upgrading `github-pages` or other gem versions unless you also validate local build and GitHub Pages behavior.

# Examples (use these patterns)

- Add a new page: create `_pages/my-page.md` with front matter:

  ---
  layout: page
  title: My Page
  permalink: /my-page/
  nav: true
  nav_order: 5
  ---

- Add a project: create `_projects/new-project.md` with front matter and content — it will be available under `/projects/new-project/`.

# What I couldn't discover automatically

- There are no automated tests or build scripts beyond the standard Jekyll/Bundler flow. If you rely on CI beyond GitHub Pages, share CI config and I will incorporate it.

# Editing guidance for AI agents

- Make minimal, targeted edits; prefer changing content files (`_pages`, `_projects`, `_data`) over large layout rewrites.
- When updating navigation or layout logic, update `_includes/header.liquid` and relevant `_layouts/*` files and run a local `bundle exec jekyll build` to verify.
- Preserve site conventions: use `relative_url`, keep `baseurl` empty, and follow front matter keys used throughout `_pages/`.

If any of the sections above are unclear or you want the agent to include more examples (e.g., a checklist for adding a new publication or a sample project file), tell me which parts to expand.
