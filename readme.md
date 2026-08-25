# THE 90I NEWS — GitHub Pages CMS

## GitHub Pages deployment
1. Extract this ZIP.
2. Upload all files/folders to the root of a GitHub repository.
3. In GitHub: Settings → Pages → Deploy from branch → `main` → `/ (root)`.
4. Open the website and go to `admin.html`.
5. Login to Admin.
6. Admin → Settings → GitHub Cloud Settings.
7. Enter GitHub Owner, Repository and Branch (`main`).
8. Create a GitHub Fine-grained Personal Access Token with **Contents: Read and write** access only for this repository, then enter it in the Admin settings. The token is kept only in the current browser session.

## Important
GitHub Pages is static hosting. It cannot run Netlify Functions. This version therefore does NOT use Netlify, Supabase, or LocalStorage as the shared database.
News, gallery, videos, contacts and settings are synchronized to `data/90i-data.json` in the GitHub repository through the GitHub Contents API. Public phones read that file from GitHub's raw content URL.

## SEO
Each news item supports SEO Meta Title, Meta Description, Keywords, Slug/Permalink and Canonical URL. NewsArticle JSON-LD, Open Graph and canonical tags are generated on the article page.

## Editor
The Admin news editor supports Bold, Italic and Underline formatting and preserves the formatting in the published article.

## GitHub Pages permalink limitation
GitHub Pages cannot provide arbitrary server-side rewrites. The working article URL is `article.html?slug=your-slug`. The Slug/Permalink value is still used for SEO/canonical URLs when supplied.
