# christiantomford.com

Personal portfolio site for Christian Tomford. Plain HTML and CSS with no build step.

Live at https://www.christiantomford.com

## What's here

| Path | What it is |
| --- | --- |
| `index.html` | The home page: intro, projects, about, contact. |
| `mandelbrot/index.html` | Mandelbrot Atlas, served at `christiantomford.com/mandelbrot/`. A single self-contained file. |
| `assets/mandelbrot-atlas.webp` | Project image (a screenshot of the atlas at Seahorse Valley). |
| `assets/countsift-report.webp` | Project image (CountSift's built-in sample report, which uses made-up customers). |
| `assets/og-image.jpg` | Preview image shown when the site is shared on LinkedIn, Slack, etc. |
| `assets/favicon.svg` | Browser tab icon (the Chicago star). |
| `resume.pdf` | Web copy of the resume, with the phone number removed. |
| `CNAME` | Tells GitHub Pages the site's domain. GitHub created it; don't delete it. |

## Updating the resume

The Resume links point to `resume.pdf` in this folder. To update it, replace that file with the new PDF and keep the name `resume.pdf`. Remove the phone number from the web copy first, since this site is public.

## Preview locally

Open `index.html` in a browser, or run a local server from this folder:

```bash
python3 -m http.server 8000
```

Then visit http://localhost:8000.

## Editing

- **Project text** lives in `index.html`, inside the two `<article class="project">` blocks.
- **Adding a project:** copy one of the `<article>` blocks and change its text, image and link.
- **Updating the atlas:** replace `mandelbrot/index.html` with the new version.
- **Colors and fonts** are CSS variables at the top of the `<style>` block in `index.html`. Dark mode follows the visitor's system setting.

## Publishing

The site is hosted on GitHub Pages, straight from the `main` branch of this repository (Settings → Pages: deploy from branch `main`, folder `/ (root)`). Every push to `main` redeploys it, usually within a minute or two.

To publish a change:

```bash
git pull
git add .
git commit -m "Describe the change"
git push
```
