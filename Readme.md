# Personal site

Plain HTML and CSS, no build step, no dependencies.

```
index.html      hero → 01 selected work → 02 writing → 03 short bio → contact
projects.html   all projects
writing.html    links out to published articles
timeline.html   work history, in order
```

Each page is fully self-contained — the CSS and JS are inlined, so any single file renders correctly on its own, with no stylesheet to lose. The trade-off: a style change means the same edit in all four `<style>` blocks.

## Deploy to GitHub Pages

1. Create a repo named `Bishopxxx.github.io` — that exact name gives you `https://bishopxxx.github.io` with no subpath.
2. Push these files to the root of `main`.
3. Settings → Pages → Deploy from a branch → `main` / `(root)`.

Custom domain later: add a `CNAME` file containing just the domain, then point a CNAME DNS record at `bishopxxx.github.io`.

## Adding an article

`writing.html` links out to wherever you publish. Copy one `<a class="row reveal">` block, change the href, the source label, the date and the text. Newest at the top. Three placeholders are in there now — delete them as real ones land. Add the best two to the `02 / Writing` section on `index.html` as well.

## Adding a project

Copy a `<a class="card reveal">` block in `projects.html`. A card without a link is a `<div class="card reveal">` instead.

## Theme

Follows the system setting on first visit. The sun/moon button overrides it and the choice is remembered per browser. The theme is applied before first paint, so there is no flash. All colours live in the `:root` and `html[data-theme="dark"]` blocks at the top of the `<style>` block in each page — change them there and both themes follow.

## Motion

Sections fade up as they enter the viewport, cards lift and grow an accent edge on hover, writing rows invert and nudge right, the header grows a hairline once you scroll, and the availability dot pulses. All of it is disabled automatically for anyone with reduced-motion turned on.

## Still needed

- `cv.pdf` in the root — the nav, hero and footer all link to it.
- The real EscrowPay repo URL. Every EscrowPay link currently points at your GitHub profile.

## Local preview

```
python3 -m http.server 8000
```