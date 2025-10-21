# Repository Guidelines

## Project Structure & Module Organization
This repository hosts a Beautiful Jekyll site. Global configuration is in `_config.yml`, navigation strings in `_data/ui-text.yml`, and reusable snippets in `_includes/`. Layouts reside in `_layouts/`, posts in `_posts/` follow the `YYYY-MM-DD-title.md` pattern, and standalone pages such as `aboutme.md` stay in the project root. Static assets live in `assets/{css,js,img}`. `_site/` is generated output; never edit it by hand.

## Build, Test, and Development Commands
Run `bundle install` once to sync Ruby dependencies. Use `bundle exec jekyll serve --livereload` for local development; it builds to `_site/` and watches for changes. Add `--drafts` when you need to preview unpublished work. For production, run `bundle exec jekyll build` to validate Liquid templates and produce a clean `_site/` folder.

## Coding Style & Naming Conventions
Every Markdown page must start with YAML front matter delimited by `---`; include `title`, `layout`, and relevant metadata. Prefer Markdown for prose, Liquid tags for templating, and keep two-space indentation in Liquid or HTML snippets. Name posts with descriptive, lower-case slugs (e.g., `_posts/2024-02-04-timegpt.md`). Place images in `assets/img/` and reference them with site-relative paths (`/assets/img/example.png`). When adjusting styling, modify the overrides in `assets/css/beautifuljekyll.css` and group selectors by component.

## Testing Guidelines
Before pushing, run `bundle exec jekyll build` to surface build or Liquid errors. Follow with `bundle exec jekyll doctor` to catch configuration issues. After builds, spot-check key pages in a local browser to confirm layouts, navigation, and assets. If you introduce new layouts or includes, add a draft page that exercises the change and preview it with the `--drafts` flag.

## Commit & Pull Request Guidelines
Keep commits focused and succinct, mirroring the existing short, descriptive titles (e.g., `TimeGPT-1`, `Phamarco`). Use the imperative mood if you add a body. For pull requests, summarize user-facing changes, attach screenshots for visual updates, and link the associated issue or discussion. Note configuration steps (e.g., `_config.yml` updates) so reviewers can reproduce the setup.

## Content & Asset Management
When adding long-form content, prefer tables or lists over raw HTML unless complex structure is required. Store downloads under `assets/` and link with absolute paths to keep GitHub Pages happy. Remove unused images or includes during refactors to keep the repository lean.
