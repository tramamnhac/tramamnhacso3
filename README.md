# Festival Landing Page + Pages CMS

## Files
- `index.html`: responsive landing page; renders from `data/site.json` when hosted.
- `data/site.json`: content edited through Pages CMS.
- `.pages.yml`: Pages CMS configuration.
- `assets/`: the 8 supplied event images.

## First setup
1. Create a GitHub repository and upload the **contents** of this folder (including hidden `.pages.yml`).
2. In GitHub repository Settings → Pages, choose the deployment method for a static site (GitHub Actions or deploy from branch). For a simple root `index.html`, deploying from the `main` branch root is sufficient.
3. Open `https://app.pagescms.org`, sign in with GitHub and install/authorize the Pages CMS GitHub App for this repository.
4. Pages CMS reads `.pages.yml`; open “Cấu hình landing page” to edit the single `data/site.json` file.
5. Commit changes in Pages CMS. GitHub Pages then serves the updated JSON and HTML. If using a custom GitHub Actions workflow, make sure it deploys the repository root and includes `data/` and `assets/`.

## Editing images
- The image fields are URL text fields intentionally, so you can paste a direct HTTPS URL from the newspaper's image server.
- Local images can use paths like `assets/hero-banner.jpg`. Keep the `assets` folder in the repository.
- If a direct URL is private, expires, or blocks hotlinking, it may not display on the public site.

## Sections and lists
- You can turn Hero, Programme, Singers, Songs and Footer on/off.
- You can add, remove and reorder menu items, singer cards, programme tags and songs.
- This initial setup supports the four designed content sections. Adding a brand-new custom section type requires adding its renderer/template in `index.html`; toggling and editing existing sections needs no code changes.

## YouTube
Paste a normal YouTube watch URL, youtu.be URL, or 11-character video ID in the `youtubeUrl` field. The video area is responsive (16:9). Leave it empty to show the placeholder.

## Local preview
Because the page fetches `data/site.json`, opening `index.html` directly as `file://` uses the embedded fallback content. To preview the latest CMS JSON locally, run a local HTTP server in this folder, for example:

```bash
python -m http.server 8000
```

Then open `http://localhost:8000`.
