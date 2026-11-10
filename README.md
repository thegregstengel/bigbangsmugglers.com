# bigbangsmugglers.com

Source for the Big Bang Smugglers marketing site, player guide, and release notes. The live site is [bigbangsmugglers.com](https://bigbangsmugglers.com).

The site is [Hugo](https://gohugo.io/) extended with no theme. Layouts, styles, and content are in this repository. GitHub Pages hosts the built site.

## Repository layout

```
content/guide/                 Player guide
content/releases/              Release notes and the February 2026 dev log
content/privacy.md             Privacy policy
content/delete-account.md      Account deletion instructions
data/                          Season readout, turn settings, guide groups, and tags
layouts/                       HTML templates and partials
assets/css/site.css            The only stylesheet
assets/img/logo-source.png     Wordmark source for icons and the social image
static/                        Favicon, web manifest, and screenshots
hugo.toml                      Site configuration
.github/workflows/hugo.yml     GitHub Actions workflow that deploys the site
```

Content conventions, design rules, and gotchas are in [CLAUDE.md](CLAUDE.md).

## Build locally

Install [Hugo extended](https://gohugo.io/installation/) 0.155.3, the version pinned in `.github/workflows/hugo.yml`.

```bash
git clone https://github.com/thegregstengel/bigbangsmugglers.com.git
cd bigbangsmugglers.com
hugo server -D
```

Open [http://localhost:1313](http://localhost:1313).

To build the site files, run `hugo --gc --minify`. Hugo writes them to `public/`.

## Publish a change

1. Create a branch named `site/<topic>`.
2. Open a pull request to `main`.
3. After you merge the pull request, GitHub Actions builds the site and deploys it to GitHub Pages.
