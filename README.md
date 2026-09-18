# HWREBench public website

The Quarto source for <https://hwrebench.com>.

## Preview and build

Install [Quarto](https://quarto.org/docs/get-started/) (the deployment workflow currently pins 1.8.27), then run:

```sh
quarto preview
```

For a static build:

```sh
quarto render
```

Rendered output is written to `_site/` and is not committed.

## Edit content

- Home: `index.qmd`
- About: `about.qmd`
- Blog listing: `blog.qmd`
- Posts: `posts/<date>-<slug>/index.qmd`
- Navigation and site settings: `_quarto.yml`
- Theme adjustments: `theme.scss`

Start a post by copying the initial post directory and changing its title, date, description and body. Add `draft: true` to a post's front matter to exclude it from the published site while writing. Draft source is still visible in this public repository. Only place material intended for public release here.

## Publishing

Push to `main` to build and deploy through GitHub Actions and GitHub Pages. Pull requests render the site without deploying it. No manually managed deploy key or token is required.

GitHub Pages is configured for `hwrebench.com`. The `CNAME` file records that hostname; for this Actions deployment, the repository's Pages custom-domain setting is authoritative. The `www` hostname redirects to the apex domain when DNS and the GitHub certificate are ready.

This repository may be checked out independently or used as the `hwrebench-public/` submodule of the private HWREBench workspace. Commit and push here first, then update the submodule reference in the parent workspace.
