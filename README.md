# Big Bang Smugglers Website

Hugo-based website for Big Bang Smugglers game. Uses the [Blowfish](https://github.com/nunocoracao/blowfish) theme.

## Structure

```
├── content/
│   ├── _index.md           # Homepage
│   ├── blog/               # Dev blog posts
│   │   ├── _index.md
│   │   └── *.md            # Individual posts
│   └── roadmap/            # Development roadmap
│       └── _index.md
├── themes/
│   └── blowfish/           # Theme (submodule)
├── hugo.toml               # Site configuration
└── .github/workflows/      # GitHub Actions for deployment
```

## Local Development

### Prerequisites
- Hugo Extended (v0.112.0 or later)

### Install Hugo

**Ubuntu/Debian:**
```bash
sudo apt update
sudo apt install hugo
```

**macOS:**
```bash
brew install hugo
```

**Snap:**
```bash
sudo snap install hugo
```

### Clone & Run

```bash
git clone https://github.com/thegregstengel/bigbangsmugglers.com.git
cd bigbangsmugglers.com
git submodule update --init --recursive
hugo server -D
```

Visit http://localhost:1313

## Creating Content

### New Blog Post

```bash
hugo new blog/my-post-title.md
```

Edit the frontmatter:
```yaml
---
title: "My Post Title"
date: 2026-02-12
draft: false
description: "Short description"
tags: ["features", "ui"]
---
```

### Update Roadmap

Edit `content/roadmap/_index.md` directly.

## Deployment

GitHub Actions automatically builds and deploys the site when you push to `main`.

## Theme Customization

Blowfish configuration lives in `hugo.toml`. See [Blowfish docs](https://blowfish.page/docs/) for customization options.

## Content Guidelines

### Blog Posts
- Use present tense for current features
- Include screenshots when showing UI
- Tag posts appropriately
- Link to related GitHub issues when relevant

### Roadmap
- Keep status accurate (✅ ✓ 🚧 📋)
- Update "Last Updated" date
- Group features logically
- Link to GitHub issues/projects

---

Built with [Hugo](https://gohugo.io/) and [Blowfish](https://blowfish.page/)
