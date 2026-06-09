---
description: Publish the latest draft from _drafts to _posts using the most recently added image, commit, push, and return the live URL
---

Publish the latest draft essay from `_drafts/` to `_posts/` on this Jekyll (Chirpy) blog, fully automatically.

Follow these steps:

1. **Find the latest draft** in `_drafts/` (most recently modified file, ignoring `post-template.md`). Read it.

2. **Find the latest image** added to `assets/img/` — the most recently modified file (e.g. an `IMG_*.jpg` you just dropped in). This is the post image.

3. **Derive the slug** from the draft title: lowercase, strip apostrophes/punctuation, spaces → hyphens (e.g. "You're Not Bad At Cold Calling" → `youre-not-bad-at-cold-calling`). Use today's date as `YYYY-MM-DD`.

4. **Rename the image** to `assets/img/<date>-<slug>.<ext>` (keep the original extension). Use `git mv` if the source is tracked, otherwise `mv`.

5. **Create the post** at `_posts/<date>-<slug>.md` with front matter matching the existing posts' style:
   ```
   ---
   title: "<Title>"
   date: <YYYY-MM-DD>
   categories: [Ship30for30, <Sales | Personal | ...>]
   tags: [<lowercase tags>]
   ---

   ![<Title>](/assets/img/<date>-<slug>.<ext>)

   <draft body, with the image embedded at the top>
   ```
   - **Always** list `Ship30for30` as the first category (exact casing), then add one topical category that fits the content (`Sales`, `Personal`, `Business`, `Industry`, ...).
   - Pick `tags` that fit the content, matching the casing/style of recent posts (tags are lowercase; keep acronyms like AI, SKO uppercase).

6. **Remove the draft** file from `_drafts/`.

7. **Commit and push**: `git add` the new post and image, commit with message `Publish '<Title>' essay`, then `git push`.

8. **Return the live URL**: `https://davistui.com/posts/<slug>/` (Chirpy default permalink). Note it may take a minute or two for GitHub Pages to rebuild.

Do all of this without asking for confirmation — just report what you published and the URL at the end.
