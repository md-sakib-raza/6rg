# Project Guide

## Architecture

This is a zero-build static Hindi news portal. Every public page is a small HTML shell. Shared rendering, seeded editorial content, storage, search, admin CRUD, galleries, video embeds, and e-paper generation live in `assets/app.js`. The complete visual system and responsive behavior live in `assets/styles.css`.

## Key files

- `index.html`: homepage shell and primary SEO metadata
- `category.html`, `article.html`, `search.html`: dynamic query-string pages
- `epaper.html`, `gallery.html`, `video.html`: media products
- `admin.html`: browser-based editorial dashboard
- `assets/app.js`: data model and all application behavior
- `assets/styles.css`: editorial design system
- `netlify.toml`: hosting, routing, caching, and headers

## Conventions

- Keep the project framework-free and build-free.
- Reuse the shared header, footer, card, and storage helpers.
- Preserve the `90i_` LocalStorage key namespace.
- Escape user-managed strings before rendering HTML.
- Keep visible interface copy in Hindi and code identifiers in English.
- Use query strings for category and article routing.

## Important decisions

Editorial data is intentionally browser-local to satisfy the client-only architecture. The e-paper is not a separate file: it is derived from article publication dates and uses the browser print dialog for PDF export. Image uploads use FileReader data URLs, so large uploads remain limited by browser storage capacity.
