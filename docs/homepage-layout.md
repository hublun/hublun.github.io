---
title: Homepage Layout Summary
layout: null
---

# Homepage Layout Summary

This document captures the major structural elements rendered on the root page (`/`) of the Beautiful Jekyll site.

- **Head**
  - Sets HTML5 metadata, responsive viewport, SEO fields (title, description, author).
  - Loads analytics snippets (`gtag`, Google Tag Manager, classic Google Analytics) and optional Cloudflare analytics include.
  - Pulls in external stylesheets for Bootstrap 4, Font Awesome 5, and Google Fonts, followed by site-specific CSS (`/assets/css/bootstrap-social.css`, `/assets/css/beautifuljekyll.css`).
  - Configures Open Graph and Twitter cards using the page title, subtitle, and avatar as defaults.
- **Navigation Bar**
  - Fixed-top Bootstrap navbar with site title linking home.
  - Contains two multi-link dropdowns (“PharmacODE”, “Dulun-LLM”), a direct link (“DRC Lab”), a single-link dropdown (“About DRC”), and a search trigger button.
  - Displays a circular avatar image (`/assets/img/handshake.png`) alongside the menu on larger screens.
- **Search Overlay**
  - Hidden overlay activated by the nav search control.
  - Provides a text input, close button, and dynamically populated results list powered by Simple Jekyll Search with pre-generated JSON data.
- **Hero Header**
  - `header-section` wrapping `intro-header` structure with centered title “Dulun R&C = DRC”.
  - Shows subtitle “Dataism ==>> electronic +  biochemical algorithms” when available.
- **Main Content**
  - Primary container (`container-md`) holding a list of recent posts.
  - Each post preview includes title, optional subtitle, publication date, thumbnail image, and truncated excerpt.
  - Clicking a preview navigates to the corresponding full post.
- **Pagination**
  - Bootstrap pagination component at the bottom of the post list.
  - Provides link to older posts (`/page2`) when more entries exist.
- **Footer**
  - Social icon links (RSS, email, GitHub) rendered with Font Awesome stacks.
  - Copyright bar displaying `CJ Duan`, current year, and link to `dulun.com`.
  - Theme attribution to Beautiful Jekyll.
- **Scripts**
  - Loads jQuery Slim, Popper.js, Bootstrap JS bundle, and the theme’s `beautifuljekyll.js`.
  - Additional analytics scripts execute at the end of the body.

Use this outline as a reference when modifying navigation, hero content, or the feed of posts to ensure changes align with the existing layout conventions.
