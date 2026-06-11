# CLAUDE.md

Personal blog for Davis Tui — a Jekyll site using the **Chirpy** theme, hosted on GitHub Pages at **https://davistui.com**.

## Layout
- `_posts/` — published essays. Filename: `YYYY-MM-DD-<slug>.md`.
- `_drafts/` — unpublished essays (plain title-cased filenames). `post-template.md` is a scaffold, not a draft.
- `assets/img/` — post images, named `YYYY-MM-DD-<slug>.<ext>` to match their post.
- `_config.yml` — site config (timezone Australia/Melbourne, lang en).

## Publishing a post
Use the `/publish` slash command — it takes the latest draft + the most recently added image and handles the slug, rename, front matter, draft deletion, commit, and push. The full procedure lives in `.claude/commands/publish.md`; the conventions it must follow are below.

Slug = title lowercased, punctuation/apostrophes stripped, spaces → hyphens. Live URL: `https://davistui.com/posts/<slug>/` (Chirpy default permalink; rebuild takes a minute or two).

## Front matter convention
```
---
title: "<Title Case Title>"
date: YYYY-MM-DD
categories: [<one category>]
tags: [<lowercase tags>]
---

![<Title>](/assets/img/<date>-<slug>.<ext>)

<body…>
```

## Conventions that matter
- **Categories** — pick exactly one, title-cased. Existing set: `Personal`, `Business`, `Sales`, `Industry`.
- **Tags** — lowercase (`sales`, `productivity`, `rugby`, `the-long-game`). **Exception:** keep acronyms uppercase (`AI`, `SKO`, `NRL`). Multi-word tags use spaces or hyphens as the topic reads naturally. Duplicate tag pages have been caused by inconsistent casing before — keep it lowercase.
- Image goes at the top of the body as `![<Title>](…)`.
- **Post images should be 16:9** — this is the preferred aspect ratio for consistency across the blog. If an image isn't 16:9, flag it before publishing (see `/publish` flow).
- Preserve the author's voice and copy exactly when moving a draft to a post — don't rewrite content.

## Git
- Default branch `main`; pushing to `main` triggers the GitHub Pages rebuild. Commit/push only when publishing or when asked.
- `.DS_Store` files are noise — don't commit them.
