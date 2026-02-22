---
# ── Required ──────────────────────────────────────────────────────────────────

title: "Post Title"

# Shown in the blog listing and og/meta tags. Keep under ~160 chars.
description: "One or two sentence summary shown in the blog listing and in link previews."

# Publication date. Controls sort order (newest first). Format: YYYY-MM-DD
pubDate: 2026-01-01

# ── Optional ──────────────────────────────────────────────────────────────────

# Shown as pill badges on the listing and post page.
tags: ["tag-one", "tag-two"]

# Full-width banner image at the top of the post. Also used for og:image.
# Put post images in public/images/blog/<slug>/
heroImage: "/images/blog/my-post/hero.jpg"

# If you revise a post after publishing, set this to show "Updated on X".
# updatedDate: 2026-02-01

# Set to false (or delete this line) when the post is ready to publish.
# While true, the post is visible in dev but hidden in production.
draft: true
---

Opening paragraph — hook the reader. No heading needed here, just drop straight into prose.

## First Section

Use `##` for top-level sections. Keep them short and scannable.

Inline images go anywhere:

![Alt text](/images/blog/my-post/detail.jpg)

<!-- Tip: images render full-width with rounded corners automatically. -->

Inline code looks like `this`, and fenced code blocks look like:

```python
def example():
    return "hello"
```

<!-- Tip: put the language name after the opening ``` for syntax highlighting. -->

## Another Section

- Bullet lists for unordered items
- Each item on its own line

1. Numbered lists for steps
2. Where order matters

> Blockquotes for callouts, pull quotes, or emphasis.

## Wrapping Up

Closing thoughts, what to read next, or a call to action.
