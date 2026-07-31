# system.straw.be

Hub site for the **Strawb System** — a plural system of four headmates sharing one physical body.

Live at [system.straw.be](https://system.straw.be)

---

## What is this?

We're a plural system. If you're not sure what that means, [MoreThanOne.info](https://morethanone.info/) is a good starting point, or see the [About page](https://system.straw.be/about) on the site itself.

This repo is the source for our system hub — a place to introduce each of us, link to our stuff, and point people to resources.

---

## Members

| Name | Pronouns | |
|------|----------|-|
| Lucy | they/them | [lucy.davinhart.me](https://lucy.davinhart.me) |
| Ivie | she/her | |
| Aurora | he/him | |
| Hol | they/them | |

---

## Tech stack

- **[Jekyll](https://jekyllrb.com/)** static site generator (Ruby)
- **SCSS** for styling, built by Jekyll
- **[Helios design tokens](https://helios.hashicorp.design/)** via CDN for colours, typography, elevation
- **[Inter](https://fonts.google.com/specimen/Inter)** font via Google Fonts
- **[Netlify](https://netlify.com)** for deployment (auto-deploys on push to `master`)
- Based on the **[minimal-categorized](https://github.com/ItsMeaga1n/minimal-categorized)** Jekyll theme

---

## Running locally

```bash
bundle install
bundle exec jekyll serve
```

Then open [http://localhost:4000](http://localhost:4000).

Requires Ruby 3.3 (see `.ruby-version` or `netlify.toml`).

---

## Site structure

| Path | File | Purpose |
|------|------|---------|
| `/` | `index.md` | Home page — member card grid |
| `/about` | `pages/about.md` | What plurality is, who we are, FAQ |
| `/lucy` | `pages/lucy.html` | Lucy's hub — links and content |
| `/ivie` | `pages/ivie.html` | Ivie's page |
| `/aurora` | `pages/aurora.html` | Aurora's page |
| `/hol` | `pages/hol.html` | Hol's page |

Navigation, member colours, and pronouns are configured in [`_data/menu.yml`](_data/menu.yml).

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

---

## Theme attribution

Based on [minimal-categorized](https://github.com/ItsMeaga1n/minimal-categorized) by [@ItsMeaga1n](https://github.com/ItsMeaga1n), MIT licensed. Substantially customised.
