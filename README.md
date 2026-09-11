# Penn Mushrooms

Source for [pennmushrooms.com](https://pennmushrooms.com), built as a static Jekyll site and hosted on GitHub Pages.

## Structure

- `index.html` — homepage
- `blog.html` — blog listing page
- `_posts/` — blog posts (Markdown, one file per post)
- `_layouts/` — page templates (`default.html`, `post.html`)
- `_includes/` — shared header/footer
- `assets/css/style.css` — all site styles
- `admin/` — [Decap CMS](https://decapcms.org) editor, available at `/admin` once GitHub OAuth is configured

## Writing a new blog post

**Option A — via GitHub directly:** add a new file to `_posts/` named
`YYYY-MM-DD-your-title.md` with front matter like:

```yaml
---
title: "Your Post Title"
description: "One or two sentences for the blog listing page."
tags: [farms]
---

Post content in Markdown goes here.
```

**Option B — via the CMS:** once GitHub OAuth is set up (see below), go to
`pennmushrooms.com/admin`, log in with GitHub, and write posts through the
editor. It commits directly to this repo.

## Local preview

Requires Ruby + Jekyll installed locally:

```
bundle install
bundle exec jekyll serve
```

Then visit `http://localhost:4000`.

## Enabling the CMS login (one-time setup)

Decap CMS needs an OAuth app to let you log in with GitHub. The simplest
route: deploy this same repo to a free Netlify site (used only for its
built-in OAuth provider — the live site can keep running on GitHub Pages),
then point `admin/config.yml`'s backend at it. See the
[Decap CMS GitHub backend docs](https://decapcms.org/docs/github-backend/)
for the exact steps.
