# Bloom — landing page

Marketing landing page for **Bloom**, a Chrome extension for design UAT:
capture any web page, mark it up in place, and land it in Figma as editable
vector layers rather than a flattened image.

## Contents

- `index.html` — the complete page. No build step, no dependencies.

Fonts (Geist, Geist Mono) load from Google Fonts; everything else — CSS, SVG,
the one small script — ships inline.

## Running it

Open `index.html` in a browser. That's the whole workflow.

## Publishing with GitHub Pages

Settings → Pages → Source: `Deploy from a branch`, branch `main`, folder `/ (root)`.
Because the file is named `index.html`, it serves at the repo's Pages URL as-is.

## Design language

Adapted from [shelf.nu](https://www.shelf.nu/), measured from the live site:

| Token | Value |
| --- | --- |
| Display / body face | Geist (700 headings, 400/500 body) |
| Mono face | Geist Mono — eyebrows, labels, code-ish detail |
| `h1` | 72px, weight 700, tracking `-0.025em`, line-height 1.08 |
| `h2` | 48px, weight 700, tracking `-0.025em` |
| Ground / text | `#FFFFFF` / `#171717` |
| Controls | 6px radius, weight 500, 14px |

Structure follows the same order: centred hero with an announcement pill above
the headline, an accent-coloured phrase inside the headline, paired primary and
outline CTAs, a microcopy trust row, then trust strip → product shot → features
→ steps → stat band → FAQ → closing CTA.

The one deliberate divergence is colour: Shelf's accent is `#CC3D00`, Bloom's is
`#C21F5B`. Swapping the `--accent*` tokens in `:root` changes it in one place.

Both light and dark themes are defined at token level, including `--on-accent`
for text sitting on the accent fill.

## Honesty note

Shelf's page leans on star-rating testimonials, a customer logo wall, and usage
statistics. Bloom is in closed UAT, so those structural slots are filled with
true content instead of invented social proof:

- the logo wall became an **integrations** strip (Figma, Chrome, Slack, Notion, Jira)
- the usage stats became **product characteristics** (capture modes, dependency
  count, vector coverage, clicks to Figma)

Do not swap real-looking testimonials in until they are real.

## Status

The email capture form is a front-end demo; it updates its own label and posts
nowhere. Wire it to a real endpoint before launch.
