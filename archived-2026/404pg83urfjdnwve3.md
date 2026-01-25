# HouseLearning Blob 404 Page and README

**What this contains**

- `404.html` — Friendly 404 page styled to match HouseLearning.
- `css/404.css` — Styles for the 404 page.
- `js/404.js` — Minimal client-side logic for search and report actions.
- `README.md` — This file.

## Purpose

This 404 page gives visitors a clear, branded experience when they hit a missing URL. It offers quick navigation, a simple search prompt, and an easy way to report broken links.

## Installation

1. Copy files to your hosting root:
   - `/404.html`
   - `/css/404.css`
   - `/js/404.js`

2. Ensure your hosting serves `/404.html` for not-found responses:
   - **GitHub Pages**: add `404.html` to the repository root (GitHub Pages automatically serves it).
   - **Firebase Hosting**: in `firebase.json` set:
     ```json
     {
       "hosting": {
         "public": "public",
         "rewrites": [],
         "cleanUrls": true,
         "trailingSlash": false,
         "errorPage": "/404.html"
       }
     }
     ```
   - **Other hosts**: consult your host docs and configure the custom 404 page to point to `/404.html`.

3. Verify links in the header and suggested links match your site structure. Edit `404.html` if your routes differ.

## Behavior

- **Go to Home** returns to the site root.
- **Search the site** prompts for a query and redirects to `/docs/forum.html?q=...` by default. Update the redirect target if you have a dedicated search page.
- **Report broken link** copies a short report to the clipboard for easy submission to your issue tracker or admin email.

## Customization

- Change colors and fonts in `css/404.css` to match your brand.
- Replace the `report` action in `js/404.js` with a POST to your reporting endpoint if you have one.
- Add analytics events in `js/404.js` to track 404 occurrences.

## Accessibility

- Buttons are keyboard focusable.
- Visuals use semantic HTML and readable contrast.
- If you add dynamic content, ensure `aria` attributes and focus management are applied.

## Troubleshooting

- If the 404 page does not appear, confirm your host is configured to serve `/404.html` for missing pages.
- If the clipboard copy fails, the browser may block clipboard access; the script falls back to showing the report text for manual copy.

## License

Use and adapt freely for HouseLearning projects. Keep attribution if you share publicly.

