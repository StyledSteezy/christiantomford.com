# christiantomford.com

Personal portfolio site for Christian Tomford. Plain HTML and CSS with no build step.

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

Any static host works. Point it at this folder, with no build command and the output directory set to the folder root.

The plan agreed earlier is GitHub plus Vercel:

1. Create a GitHub repository (for example `portfolio`) and push this folder to it.
2. In Vercel, import the repository. Framework preset: **Other**. Leave the build command empty. Output directory: the repository root.
3. In the Vercel project's domain settings, add `christiantomford.com` and `www.christiantomford.com`. Vercel then shows the DNS records to create.
4. In Squarespace Domains (account.squarespace.com → Domains → christiantomford.com → DNS), replace the current website records with the ones Vercel shows. Today those are the apex forwarding to `www` and the `www` CNAME to `ghs.googlehosted.com` (the Google Sites placeholder).
5. **Do not touch the MX or TXT records.** They run Google Workspace email for the domain.

After that, every `git push` to the repository redeploys the site.
