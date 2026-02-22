---
# ── Required ──────────────────────────────────────────────────────────────────

title: "Project Title"

# Shown on the listing card and in og/meta tags. Keep under ~160 chars.
description: "One or two sentence summary shown on the projects listing and in link previews."

# ── Optional ──────────────────────────────────────────────────────────────────

tags: ["tag-one", "tag-two", "tag-three"] # Shown as pill badges on the listing and detail page.
heroImage: "/images/projects/my-project/hero.jpg" # First image shown as the full-width banner. Also used for og:image.
# Put project images in public/images/projects/<slug>/
githubUrl: "https://github.com/username/repo" # If set, renders a "GitHub →" link in the project header.
liveUrl: "https://example.com"  # If set, renders a "Live site →" link in the project header.
order: 99 # Controls sort order on the /projects listing. Lower = higher up.
draft: true # While true, the project is visible in dev but hidden in production.

---

Brief intro paragraph — what the project is and why it exists. This shows up right below the title/description on the project page. No heading needed here.

## Background

More context, motivation, or problem statement. Use `##` headings to organize sections.

## How It Works

Explain the technical approach, architecture, or process. Use lists for steps:

- First thing
- Second thing
- Third thing

Inline images go anywhere in the body with standard Markdown:

![Alt text describing the image](/images/projects/my-project/detail.jpg)

<!-- Tip: you can add as many images as you want inline — no separate gallery needed. -->

## Results / Outcome

What came out of it? Metrics, lessons learned, what you'd do differently.

## Links

- [GitHub repo](https://github.com/username/repo)
- [Related blog post](/blog/my-blog-post)
