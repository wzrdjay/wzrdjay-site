# wzrdjay.com — portfolio site

Static two-page portfolio. No build step, no dependencies.

## Structure

- `index.html` — Work page (project grid + filters)
- `services.html` — Services page
- `images/` — all project photos and logos
  - `logo-0.png`, `logo-1.png` — brand mark + wordmark
  - `work-00.jpg` … — project images

## Edit the work

Open `index.html`, find the `WORK` array near the bottom (inside `<script>`).
Each project looks like:

```js
{
  type: "graphic",            // "graphic" or "photo"
  title: "Project name",
  client: "Client name",
  year: "2025",
  role: "Your role",
  poster: "images/work-00.jpg",     // the cover/thumbnail
  gallery: ["images/work-00.jpg", "images/work-01.jpg"]  // all images in the set
}
```

To add a project: drop the image(s) into `images/`, copy an existing block,
update the fields and image paths. Order in the array = order on the page.

## Deploy (GitHub + Netlify — set up once)

1. Create a new GitHub repo and push this folder:
   ```
   git init
   git add .
   git commit -m "Portfolio site"
   git branch -M main
   git remote add origin git@github.com:<you>/wzrdjay-site.git
   git push -u origin main
   ```
2. In Netlify: Add new site → Import from Git → pick this repo.
   - Build command: (leave empty)
   - Publish directory: `.`
3. Netlify gives you a URL. Under Domain settings, add `wzrdjay.com`
   and follow the DNS steps. HTTPS is automatic.

After that, every `git push` redeploys the site automatically — no dragging files.

## Quick deploy (no Git)

Drag this whole folder onto https://app.netlify.com/drop
