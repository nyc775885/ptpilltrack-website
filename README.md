# ptpilltrack-website

Public website for the Pill Tracker mobile app. Hosts the landing page, Privacy Policy, and Terms of Service at <https://ptpilltrack.com>.

## Structure

```
.
├── index.html          # landing page at /
├── privacy/
│   └── index.html      # /privacy
├── terms/
│   └── index.html      # /terms
├── style.css           # shared stylesheet
└── README.md           # this file
```

URLs are served by Cloudflare Pages. Any folder with `index.html` is reachable at `/folder-name/` without a file extension.

## Editing

1. Edit the HTML file(s) locally.
2. Preview in a browser by double-clicking `index.html` — it works standalone.
3. Commit and push:
   ```bash
   git add .
   git commit -m "Update privacy policy"
   git push
   ```
4. Cloudflare Pages auto-deploys within ~30 seconds of the push. Visit ptpilltrack.com to verify.

## Updating the effective date

When you change legal content, bump the `Last updated` date at the top of `privacy/index.html` or `terms/index.html`. For material changes, also consider sending an in-app notice in the Pill Tracker app.

The canonical Markdown source of these docs lives in the app repo at `pill-tracker/legal/`. Keep the HTML here and the Markdown there in sync when making substantive edits.

## Hosting

- **DNS & CDN & static site**: Cloudflare Pages (free plan)
- **Email forwarding**: Cloudflare Email Routing (free) — `support@ptpilltrack.com` forwards to personal Gmail
- **Domain registrar**: Porkbun (where the domain is renewed)

## Local testing

Just open `index.html` in a browser. Because all assets use absolute paths from root (`/style.css`), you may want to serve the folder with a mini HTTP server for accurate path resolution:

```bash
# Python 3
python -m http.server 8000
# → http://localhost:8000
```
