# bigbangsmugglers.com

Marketing site, player guide, and release notes for Big Bang Smugglers.

The site is mid-redesign (Sept 2026). The approved plan, design tokens and
page templates are in the review artifact linked from Claude's memory
(`site-redesign-plan`). Phases: 0 content hygiene ✓, 1 foundation ✓,
2 guide, 3 releases (section renamed to `/releases/`), 4 homepage,
5 search/RSS/polish, 6 live season metrics in the HUD.

---

# Tech stack

- Hugo extended (v0.155.3, pinned in CI) — no theme, all layouts are ours
- One stylesheet, `assets/css/site.css`, built through Hugo Pipes
- Google Fonts: Nunito Sans (everything humans read) + JetBrains Mono (numbers, versions, formulas)
- GitHub Actions → GitHub Pages

---

# Repo structure

```
content/
  guide/                 # Player guide (21 pages; front matter: group, tags, changed_in)
  release-notes/         # Releases + Feb 2026 dev log (front matter: entry, version, tags)
  privacy.md
  delete-account.md
data/
  site.yaml              # season status, store/community links (HUD + footer)
assets/css/site.css      # tokens + components; the only stylesheet
layouts/
  baseof.html            # shared chrome: head, HUD header, main, tab bar, footer
  home.html              # homepage (inline-styled sections until Phase 4)
  docs/{list,single}.html    # guide (type: docs)
  blog/{list,single}.html    # release notes (type: blog)
  page.html              # privacy, delete-account
  404.html, robots.txt, index.json (search index)
  _partials/             # head, header, footer, tabbar, search, icon, tw-rights
  _markup/render-table.html  # wraps every markdown table in .table-wrap
static/                  # favicon set, og-image.png, site.webmanifest, logo
hugo.toml
.github/workflows/hugo.yml
```

---

# Common commands

- Dev server: `hugo server -D`
- Production build: `hugo --gc --minify`
- Hugo is not installed on wopr; download the extended binary into the session scratchpad to build locally.

---

# Content conventions

## Release notes

Helper: `~/.aiops/scripts/bbs-release-notes-site "<filename>.md" "v<version> -- <Title>"`

Or create `content/release-notes/YYYY-MM-DD-vX-Y-Z-slug.md`:

```yaml
---
title: "v2.4.0 — Title"
date: 2026-10-01T12:00:00Z    # always explicit UTC
type: blog
description: ""
entry: release                # release | devlog
version: 2.4.0                # releases only
tags: [planets, combat]
---
```

The HUD "Build" readout is the newest `entry: release` note's `version`.
Release-note commits: "Release notes: v[VERSION]".

## Guide

Every guide page carries `group`, `tags` and `changed_in` (the release
versions that changed it). Never write "accurate as of vX" in prose; add the
version to `changed_in` and say "since vX" inline where a rule changed.

Guide groups: start, fly, trade, fight, build, compete, numbers.

## Shared tags (guide + releases)

planets, starbases, corps, combat, bounties, ordnance, trading, ports,
smuggling, ships, upgrades, seasons, progression, missions, navigation,
factions, npcs, platform.

Do not use `kind` as a front matter key — Hugo reserves it.

---

# Design rules

- Colors come from the tokens in `site.css`; never hard-code hex in layouts.
- Mint is the only interactive color. Gold = credits/season, coral =
  pirate/danger, sky = Federation/info, violet = epic. Semantic, not decorative.
- Mono only for numbers, versions, formulas. Sans for labels and headings.
- Phone first: nothing wider than the screen; tables scroll inside `.table-wrap`.
- The tab bar renders only on guide and release pages (see `baseof.html`).
- The Trade Wars rights notice in `_partials/tw-rights.html` is never reworded
  and must appear on every page (it does, via the footer).

---

# Deployment

Push to `main` → GitHub Actions installs Hugo, runs `hugo --gc --minify`,
deploys to GitHub Pages. No manual steps. Custom domain: `bigbangsmugglers.com`.

Work happens on branches with PRs to `main` (`site/phase-N-…` for redesign work).

---

# Gotchas

- Hugo resolves layouts by front-matter `type`: guide pages cascade `type: docs`
  and release notes set `type: blog`, so their layouts live in `layouts/docs/`
  and `layouts/blog/`, not `layouts/guide/` or `layouts/release-notes/`.
- Taxonomy pages are disabled in `hugo.toml` until Phase 3 gives tags a layout.
- Unsafe HTML rendering is on in `hugo.toml` for custom content.
- Hugo extended is required.

---

# Shared knowledge base (Obsidian vault)

Durable docs for this site live in the shared vault at `~/nas/Obsidian/`:

- `20-Protovision/big-bang-smugglers/bigbangsmugglers-com-profile.md` -- project profile

See `~/nas/Obsidian/CLAUDE.md` for vault rules; use the `doc-writer-obsidian`
skill to publish new docs. The vault is Greg's and Claude's shared long-term
memory across machines.
