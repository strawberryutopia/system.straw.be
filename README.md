# system.straw.be

Hub site for the Strawb System. Live at [system.straw.be](https://system.straw.be)

---

## Tech stack

- **[Jekyll](https://jekyllrb.com/)** static site generator (Ruby)
- **SCSS** for styling, built by Jekyll
- **[HashiCorp Helios design tokens](https://helios.hashicorp.design/)** via CDN for colours, typography, elevation — not because it needs them, but because it was an amusing idea
- **[Inter](https://fonts.google.com/specimen/Inter)** font via Google Fonts
- **[Netlify](https://netlify.com)** for deployment (auto-deploys on push to `master`)
- Originally based on the **[minimal-categorized](https://github.com/ItsMeaga1n/minimal-categorized)** Jekyll theme — though there's basically nothing left of it at this point

---

## Running locally

```bash
bundle install
bundle exec jekyll serve
```

Then open [http://localhost:4000](http://localhost:4000).

Requires Ruby 3.3 (pinned in `netlify.toml`).

---

## Adding content for a member

Create a file in `_posts/` with the member's `category` in the front matter:

```markdown
---
layout: post
no_date: true
title: Some Link Title
category: lucy
external_url: https://example.com
external_name: example.com
summary: A short description shown on the hub page.
---
```

The post will automatically appear on that member's hub page (`/lucy`, `/ivie`, etc.).

---

## Deployment

Pushes to `master` automatically deploy to Netlify. Build config is in [`netlify.toml`](netlify.toml):

```toml
[build]
  command = "bundle exec jekyll build"
  publish = "_site"
```
