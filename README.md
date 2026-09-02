# Bloom — landing page

Marketing landing page for **Bloom**, a Chrome extension for design UAT:
capture any web page, mark it up in place, and land it in Figma as editable
vector layers rather than a flattened image.

## Contents

- `index.html` — the complete page. No build step, no dependencies.

Fonts (Fraunces, Instrument Sans, DM Mono) load from Google Fonts; everything
else — CSS, SVG, the one small script — ships inline.

## Running it

Open `index.html` in a browser. That's the whole workflow.

## Publishing with GitHub Pages

Settings → Pages → Source: `Deploy from a branch`, branch `main`, folder `/ (root)`.
Because the file is named `index.html`, it serves at the repo's Pages URL as-is.

## Design notes

The page is built on a risograph colour-separation idea: a riso print is
assembled from separate ink layers that overprint into one image, which is
exactly what Bloom does to a screenshot. The hero visual fans a single capture
into three labelled separations — capture, frame, markup.

- Palette: sage newsprint `#EFF1E8`, riso teal `#007A73`, fluorescent pink `#D62C74`
- Type: Fraunces (display) / Instrument Sans (body) / DM Mono (labels)
- Both light and dark themes are defined at token level

The hero uses `mix-blend-mode: multiply`, which composites against whatever sits
behind it. `.stage` therefore owns an opaque light backdrop and `isolation: isolate`
so the blend stays confined — without that, dark mode crushes the visual to black.

## Status

The email capture form is a front-end demo; it updates its own label and posts
nowhere. Wire it to a real endpoint before launch.
