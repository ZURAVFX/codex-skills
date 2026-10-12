# Landing pages

A public release with a download gets a landing page that carries someone from "what is this" to "installed and running". It should read as part of zuravfx.com, not as a separate product microsite.

## What "less AI" means here

The current ZURA OCIO Look page is the old look. Do not copy it. Its tells:

- A dark near-black canvas with a purple accent and a dark radial glow behind the hero.
- Rounded 18 to 24px cards and pill badges with uppercase tracking.
- A giant negative-tracking headline above three-column feature cards.
- A fake "effect controls" mockup drawn in CSS.

zuravfx.com is instead a white studio contact sheet: hairline rules, a large but neutral headline, unframed editorial bands, and one consistent media treatment. Match that.

## Palette

- Canvas `#ffffff`, ink `#111111`
- Media well `#e8e8e8`, well deep `#dedede`
- Hairline `#d2d2d2`
- Mask blue `#5f6fff`, accent only: rules, mask paths, hover, small labels
- Quiet grey `#686868`

Do not introduce a second accent colour, gradients or glows.

## Typography

- Inter Tight throughout, weights 400 to 700.
- Letter spacing stays neutral. Do not tighten display headings.
- Headings are weight 600.

## The mask signature

Every image or video sits inside a rectangular After Effects-style mask path: a 1.25px `#5f6fff` border with one small square vertex at each 90-degree corner. No rounded corners, no handles, no offset contours. The template already does this with `.mask-frame`.

## Hero media

- The hero shows a **real capture of the tool**: a genuine screenshot, a still from a real render, or the product image already on zuravfx.com.
- Never draw a fake interface in CSS, and never leave a placeholder graphic. The old ZURA OCIO Look page did exactly that with its mock effect-controls panel; do not repeat it.
- Capture it yourself when you can. For a web or browser tool, screenshot it headlessly. For a desktop app, capture the window. Then optimise the image and place it in the repository's `docs/` folder beside `index.html`.
- Keep it at the tool's natural aspect ratio inside the mask. 16:9 suits most interface captures; use `aspect-ratio` on `.mask-frame` to match.

## Structure that works

1. **Header**: wordmark linking back to zuravfx.com, plus links to the download and the GitHub repository.
2. **Intro band**: small uppercase kicker naming software and platform, the headline as a plain statement of what the tool is, a short lede, then primary and secondary actions. The tool media follows immediately, inside the mask.
3. **What it does**: a short paragraph and numbered capability rows separated by hairlines. Rows, not cards.
4. **Workflow**: numbered steps for using the tool in a real pipeline.
5. **Install**: numbered steps, the download action repeated, and a link to the issues page for compatibility reports.
6. **Note band**: the important caveat, what the tool is not, as a band with a blue left edge rather than a coloured card.
7. **Footer**: name, role, links and year, matching the site footer.

Bands run full width with a constrained inner column and 1px separators. Keep motion restrained: a slight settle as a band enters view, no parallax.

Never hide content behind an opacity fade. Text and rows must be fully legible before any reveal runs, without scrolling, in a screenshot, and with JavaScript disabled. Animate transform only, never opacity from zero. A screenshot or a reader who does not scroll should still see the whole page.

## Copy

- Lead with what the tool does for the artist, in the artist's words.
- Keep the "what it is not" caveat honest and specific.
- UK English, no em dashes, no emojis.
- Do not invent prices, licence terms or compatibility claims.

## Checklist

- Opens with no build step, as a single self-contained `index.html` in `docs/`.
- Readable at 360px wide, with the header collapsing cleanly.
- Download links resolve to the real asset.
- Reduced-motion preferences disable reveals.
