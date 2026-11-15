# mrazizi.com

Minimal static portfolio for Mohammad-Reza Azizi.

## Profile photo

The photo lives at:

```text
assets/profile.jpg
```

To change it, replace that file with a square JPG, at least 600 × 600 px, under 500 KB. If it's missing, the site falls back to the initials placeholder.

## Preview locally

GitHub Pages builds this site with Jekyll. To preview it with the same gems (no local Ruby needed):

```bash
docker run --rm -p 127.0.0.1:4000:4000 -v "$PWD":/srv/site -v mrazizi-gems:/usr/local/bundle -w /srv/site ruby:3.3 sh -c 'bundle install && bundle exec jekyll serve --host 0.0.0.0 -d /tmp/_site --force_polling'
```

Then open `http://localhost:4000`. With Ruby installed, `bundle install && bundle exec jekyll serve` works too.

## Write a blog post

Add `_posts/YYYY-MM-DD-slug.md`:

```markdown
---
layout: post
title: My post title
description: One-line summary for search and link previews.
---

Post body in Markdown.
```

Push to `main` and it appears at the top of `/blog/`. `_posts/2026-11-15-hello-world.md` is a placeholder; delete it once a real post exists.

## Update experience

Roles live in `_data/experience.yml` (copied from the master CV).

## Publish with GitHub Pages

1. Create a public repository named `mrazizi.github.io`.
2. Upload all files in this folder to the repository root.
3. In **Settings → Pages**, choose **Deploy from a branch**.
4. Select the `main` branch and `/(root)`, then save.
5. Under **Custom domain**, enter `mrazizi.com` and save.
6. Configure your DNS records as described below.
7. After DNS is valid, enable **Enforce HTTPS**.

## DNS records

For the apex/root domain, add these four A records:

| Type | Name | Value |
|---|---|---|
| A | @ | 185.199.108.153 |
| A | @ | 185.199.109.153 |
| A | @ | 185.199.110.153 |
| A | @ | 185.199.111.153 |

For `www`, add:

| Type | Name | Value |
|---|---|---|
| CNAME | www | mrazizi.github.io |

Remove conflicting parking, forwarding, A, AAAA, or CNAME records for `@` and `www` before adding these.
