# NYM Portfolio

This repository contains the static export of [itsnym.com](https://itsnym.com/). Edit the checked-in HTML and assets directly. The repository root is the publish directory.

## Preview Locally

Run this command from the repository root.

```sh
python3 -m http.server 8765 --bind 127.0.0.1
```

Open [http://127.0.0.1:8765/](http://127.0.0.1:8765/).

## Find and Edit Pages

| Page | URL path | Source |
| --- | --- | --- |
| Home | `/` | [index.html](index.html) |
| Work | `/portfolio-item/work/` | [portfolio-item/work/index.html](portfolio-item/work/index.html) |
| About | `/about/` | [about/index.html](about/index.html) |
| Team | `/our-team/` | [our-team/index.html](our-team/index.html) |
| Album | `/portfolio-category/album-2/` | [portfolio-category/album-2/index.html](portfolio-category/album-2/index.html) |

The `/work/` and `/team/` pages redirect to Work and Team. Use relative links for navigation and assets so the site works under a GitHub Pages project path. If you change a public route, update its canonical URL and [sitemap.xml](sitemap.xml).

Page-specific styles live in [assets/css](assets/css). The exported theme, fonts, and browser libraries live in [assets/vendor](assets/vendor).

## Update the Work Gallery

Store the full-resolution image in [assets/images/original](assets/images/original) and a smaller WebP thumbnail in [assets/images/gallery](assets/images/gallery). In the Work page, point the gallery link's `href` and `data-src` to the full-resolution image and the nested image's `src` to the thumbnail. Set the image dimensions and alt text, and use `loading="lazy"` for entries below the first rows.

After an edit, check the page on desktop and mobile. Open a gallery image, advance to the next image, and close the lightbox.

## Deploy

- **GitHub Pages** — Publish from the `main` branch and the root folder. [.nojekyll](.nojekyll) lets GitHub Pages serve the existing files directly. [GitHub Pages publishing settings](https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site)
- **Vercel** — Import the repository. [vercel.json](vercel.json) configures a static deployment from the repository root. [Vercel build settings](https://vercel.com/docs/builds/configure-a-build)
