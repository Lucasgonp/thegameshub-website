# The Games Hub website

Static site for [thegameshub.com.br](https://thegameshub.com.br), the public home of the The Games Hub iPhone app. Product decisions and proposals for the site live in the app repository, in `docs/product/global/website.md` and `docs/product/website/`. Read them before adding anything.

## Rules

- **This repository is public.** Never commit secrets, personal data, internal notes or drafts that are not meant for visitors.
- **Pushing to `main` publishes.** GitHub Pages serves `main` in about a minute. Preview locally and get the owner's yes before pushing.
- **Keep it simple.** Plain HTML and CSS, no framework, no build step, no external libraries and no cookies. The app has about 100 users.
- **Copy in Brazilian Portuguese.** Code, comments, commit messages and this file in English. Talk to the owner in Brazilian Portuguese.
- **Legal pages** (`privacidade.html`, `termos.html`, `regras.html`) carry the text the owner approved, built from `docs/launch/` in the app repository. Change them only with the owner's yes, and update the date on the page.
- **Do not change `CNAME`, `.nojekyll` or `google19b89c97000b4372.html`.** `CNAME` holds the custom domain, `.nojekyll` lets GitHub Pages serve dot folders such as `.well-known`, and the Google file keeps the Search Console verification.

## Structure

| Path | Purpose |
|---|---|
| `index.html`, `suporte.html`, `privacidade.html`, `termos.html`, `regras.html` | Pages, each with its own title, description, canonical URL and link preview tags |
| `404.html` | Shown by GitHub Pages for any missing address. Uses root-absolute paths |
| `style.css` | One stylesheet with light and dark tokens on `:root` |
| `assets/` | Mascot, wordmarks, favicon and the 1200 × 630 link preview image `og.jpg` |
| `apple-touch-icon.png` | 180 × 180 icon for the iPhone home screen |
| `robots.txt`, `sitemap.xml` | Search engine files. Add every new page to the sitemap |

Use root-absolute paths (`/style.css`, `/assets/…`) in every page. Brand files come from the app repository Canvas, `design/canvas/brand/`, and follow its visual identity: Turquoise palette, Barlow Condensed for titles and Barlow for text.

## Preview

```bash
python3 -m http.server 8765
```

Check each changed page at phone and desktop widths, in light and dark.

## When adding a page

1. Copy the head and header of an existing page and set its own title, description, canonical and `og:` tags.
2. Add it to `sitemap.xml`.
3. Update `docs/product/global/website.md` in the app repository.
