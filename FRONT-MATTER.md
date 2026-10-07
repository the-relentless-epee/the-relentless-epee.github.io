---
published: false
---

# Jekyll / Minimal Mistakes Front Matter Reference

The block between the `---` fences at the top of a Markdown file is YAML **front matter**. It is per-file: every page and every post can have its own. Keys are case-sensitive, indentation matters, and tabs are not allowed.

Theme: **Minimal Mistakes 4.28.1**.

Unknown keys are not errors. Jekyll stores them and you can read them as `page.<key>`, so custom keys are allowed.

---

## 1. Jekyll core keys (valid on any page/post)

| Key | Meaning |
|---|---|
| `layout` | Which layout to use: `home`, `single`, `archive`, `splash`, `page`, `categories`, `tags`, `collection`, `search` |
| `title` | Heading / browser title |
| `permalink` | Override the output URL (e.g. `/about/`) |
| `date` | Post date (`YYYY-MM-DD`) |
| `last_modified_at` | Shows "Updated:" and `article:modified_time` |
| `category` / `categories` | Post categories |
| `tag` / `tags` | Post tags |
| `excerpt` | Manual summary used in listings and meta tags |
| `published: false` | Don't build this file |
| `description` | Meta description |
| `author` / `authors` | Per-page author override |
| `locale` | Language for UI strings |
| `direction` | `ltr` / `rtl` |
| `canonical_url` | Override the canonical link |
| `classes` | Extra CSS classes on `<body>`; `classes: wide` widens the content |
| `search: false` | Exclude from site search |
| `sitemap: false` | Exclude from `sitemap.xml` (jekyll-sitemap plugin) |

---

## 2. Minimal Mistakes theme keys

### `header:` map

Used by `page__hero.html` / `page__hero_video.html`.

| Key | Meaning |
|---|---|
| `header.image` | Plain hero/banner image (full-width, no overlay) |
| `header.image_description` | Alt text for `header.image` |
| `header.overlay_image` | Hero background with the title overlaid on top |
| `header.overlay_color` | Overlay background color (solid hero, no image) |
| `header.overlay_filter` | Darken/tint overlay: `0.5`, `rgba(...)`, or `gradient` |
| `header.show_overlay_excerpt` | `false` hides the excerpt in an overlay hero |
| `header.video: {id, provider}` | Background video instead of an image |
| `header.teaser` | Thumbnail in grid listings + `og:image` |
| `header.caption` | Caption under the hero |
| `header.og_image` / `header.og_image_alt` | Social-share image override |
| `header.actions: [{label, url}]` | Buttons rendered inside an overlay hero |

### Page-level keys

| Key | Meaning |
|---|---|
| `tagline` | Subtitle under the title in an overlay hero |
| `sidebar` | List of `{title, image, image_alt, text, nav}` blocks for the side column |
| `author_profile` | `true` / `false` show the author card in the sidebar |
| `toc` | `true` shows the "On this page" table of contents |
| `toc_label` / `toc_icon` / `toc_sticky` | TOC heading text, icon, stickiness |
| `read_time` | Show "N minute read" |
| `show_date` | Show the date in the page meta |
| `date_format` | Override date format |
| `words_per_minute` | Read-time speed (default 200) |
| `comments` | `true` / `false` enable comments on this page |
| `share` | `true` shows social share buttons |
| `related` | `true` shows related posts |
| `entries_layout` | `list` or `grid` for the post listing |
| `link` | Adds a "Direct Link" button |
| `breadcrumbs` | `true` / `false` override site breadcrumbs |
| `analytics: false` | Skip analytics on this page |

### Collection / generated archive pages only

Set these only on generated pages; you normally don't write them by hand.

| Key | Meaning |
|---|---|
| `collection` | Which collection to list (`collection` layout) |
| `sort_by` / `sort_order` | Collection sort field and direction |
| `taxonomy` | Taxonomy name (auto-generated `category` / `tag` pages) |
| `posts` | Posts belonging to the auto-generated taxonomy page |

---

## 3. Which keys matter for which layout

- `layout: home` (inherits `archive`): `title`, `header.*`, `sidebar`, `author_profile`, `entries_layout`, `classes`.
- `layout: single` (posts and About): `title`, `header.*`, `sidebar`, `author_profile`, `toc` / `toc_label` / `toc_icon` / `toc_sticky`, `share`, `related`, `comments`, `read_time`, `show_date`, `link`, `breadcrumbs`, `classes`, plus `date` / `categories` / `tags` for posts.
- `layout: splash`: mainly `header.overlay_*`, `header.actions`, `excerpt`.
- `layout: archive` / `collection` / `category` / `tag`: `entries_layout`, `header.*`, `sidebar`.

`toc`, `share`, `comments`, `read_time` etc. have no effect on `index.md` (the `home` layout never calls those includes). `entries_layout` has no effect on a `single` post.

---

## 4. Per-post example

```yaml
---
layout: single
title:  "Tips for Mounting Ball Bearings"
date:   2026-06-19
categories: notes
header:
  image: /images/bearing.jpg
  image_description: "Ball bearing"
toc: true
toc_sticky: true
share: true
---
```

---

## 5. Caveats for this site

- `_config.yml` has **no `defaults:` block**, so `layout` and `categories` must be set explicitly in every file. Adding a `defaults:` section would avoid repeating `layout: single` for posts.
- `redirect_from` / `redirect_to` do nothing here: `jekyll-redirect-from` is not in the `plugins:` list.
- `math` is not supported without an extra plugin.
- A file with no front matter at all is copied as a static file rather than rendered as a page.
