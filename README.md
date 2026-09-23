# bigbangsmugglers.com

Marketing site, player guide and release notes for **Big Bang Smugglers**,
built with [Hugo](https://gohugo.io/) and deployed to GitHub Pages.

## Structure

```
content/
  guide/            Player guide (21 pages, grouped by front matter)
  releases/         Releases (v1.1.0 →) and the Feb 2026 dev log
  privacy.md        Privacy policy
  delete-account.md Account deletion instructions
assets/css/site.css The only stylesheet (tokens + components)
data/site.yaml      Season status and store/community links
layouts/            Base layout, page templates, partials (see CLAUDE.md)
static/             Logo and favicon
hugo.toml           Site configuration
.github/workflows/  Build and deploy on push to main
```

## Local development

Requires **Hugo extended** 0.155 or later.

```bash
git clone https://github.com/thegregstengel/bigbangsmugglers.com.git
cd bigbangsmugglers.com
hugo server -D
```

Visit http://localhost:1313.

## Adding a release note

```bash
~/.aiops/scripts/bbs-release-notes-site "<filename>.md" "v<version> -- <Title>"
```

Or create a file in `content/releases/` by hand. Every note needs
`title`, `date` (explicit UTC), `description`, `entry`
(`release` or `devlog`), `version` (releases only) and `tags`. The tag list
and guide conventions live in `CLAUDE.md`.

## Deployment

Pushing to `main` builds the site with `hugo --gc --minify` and deploys it
to GitHub Pages. There are no manual steps.
