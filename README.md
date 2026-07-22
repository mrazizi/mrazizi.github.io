# mrazizi.com

Minimal static portfolio for Mohammad-Reza Azizi.

## Add your profile photo

Place your photo at:

```text
assets/profile.jpg
```

Recommended: a square JPG, at least 600 × 600 px, under 500 KB. Until then, the site shows the included initials placeholder.

## Preview locally

From this directory:

```bash
python3 -m http.server 8080
```

Then open `http://localhost:8080`.

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
