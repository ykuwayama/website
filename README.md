# yusuke-kuwayama.com

Static rebuild of the Wix site: plain HTML and CSS, with no build step and no dependencies.

## Files to add before going live

Download these from your Wix site (Wix dashboard → Media, or right-click → Save on the live pages) and save them under these exact names:

| Save as | What it is |
|---|---|
| `assets/img/yusuke.jpg` | Home page portrait |
| `assets/img/lecturing.jpg` | About Me photo |
| `assets/img/research-banner.jpg` | *Optional* wide banner on the Research page. The current irrigation photo is Wix stock media, which may only be licensed for use on Wix sites. Use your own photo or a free one (e.g., from Unsplash). If this file is missing, the page hides the banner. |
| `files/cv.pdf` | CV (linked from the Home page "CV" button) |
| `files/syllabus-publ602.pdf` | PUBL 602 syllabus |
| `files/syllabus-publ604.pdf` | PUBL 604 syllabus |
| `files/syllabus-publ608.pdf` | PUBL 608 syllabus |
| `files/syllabus-publ610.pdf` | PUBL 610-04 syllabus |

## Editing

Each page is a single `.html` file, so to add a publication, copy an existing `<p>…</p>` entry in `publications.html` and edit it. Colors and fonts are in `assets/style.css`.

## Publishing on GitHub Pages (free)

1. Create a GitHub repository (e.g., `website`) and upload the **contents** of this folder to it (drag and drop on github.com works).
2. Go to the repository's **Settings → Pages**. Set **Source** to "Deploy from a branch", choose branch `main` and folder `/ (root)`, then click **Save**.
3. Under **Custom domain**, enter `www.yusuke-kuwayama.com` and click **Save**. (The `CNAME` file in this folder already contains it.)
4. In Wix, go to **Domains → ⋯ next to yusuke-kuwayama.com → Manage DNS Records** and set:
   - **A records** (Host Name blank or `@`), replacing the existing Wix A record:
     `185.199.108.153`, `185.199.109.153`, `185.199.110.153`, `185.199.111.153`
   - **CNAME** for `www` → `<your-github-username>.github.io`
   - Leave **MX/TXT** records alone if you use email on this domain.
5. Once DNS updates (minutes to a few hours), go back to **Settings → Pages** and tick **Enforce HTTPS**.
6. After the new site is confirmed live, you can cancel the Wix *site* plan. **Keep the domain registration active.** Its renewal is billed separately, and you can later transfer the domain to another registrar (e.g., Cloudflare or Namecheap) if you prefer.

The old URLs (`/about-me`, `/research`, `/publications`, `/teaching`) keep working on GitHub Pages.
