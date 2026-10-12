---
name: zura-releases
description: Ship, back up and present Elliot's Zura / OA Motion projects. Use when releasing a project, publishing a download, backing up source development files, or adding or restyling a project landing page. Covers public ZURAVFX releases and private OA-Motion plugin releases.
---

# Zura Releases

How Elliot ships projects: where each kind of release lives, how source is backed up so work can continue from any machine with GitHub access, and how a release gets a landing page that matches zuravfx.com.

## The three parts of a release

1. **A home for the release**, public or private depending on the project.
2. **Source development files backed up** to the private monorepo. This is not optional, and it applies to public and private projects alike.
3. **A landing page** where the project warrants one.

## Where each release goes

- **Public final release** goes to a public repository under `ZURAVFX/<Project>`, and an entry is rolled onto **zuravfx.com**: add the tool to the `tools` array in `src/data/site.json`, and put its catalogue image in `public/products/`, both in the `ZURAVFX/portfolio` repo.
- **Private release** goes to `OA-Motion/OA_Motion_Software_Plugins`, under the folder for its software. Built installers go in `software/`; per-software source and tools go under `Blender/`, `After-effects/`, `C4D/` or `Davinci-Resolve/`.
- **Source development files, always**, go to `OA-Motion/project_development_files`, one folder per project, pushed so the project can be picked up from anywhere with GitHub access.

Read [references/destinations.md](references/destinations.md) before pushing anywhere. It holds the exact repos, paths, branch and publishing details, plus the rules already recorded in that monorepo.

## Public or private

Infer it from the project rather than asking: finished user-facing tools and plug-ins with a download are public; internal OA Motion tooling, and anything not meant to be distributed publicly, is private. Ask only when it is genuinely ambiguous.

## Landing pages

A public release with a download should have a landing page that carries someone from "what is this" to "installed and running".

- Host it on GitHub Pages from the repository's `docs/` folder on `main`, as a self-contained static page. `docs/index.html` is the convention already in use.
- Make it look like **zuravfx.com**, not a generic dark AI landing page. The current ZURA OCIO Look page is the old look and should not be copied: no purple accent, no dark radial glow, no rounded 18 to 24px cards, no pill badges.
- Start from [assets/landing-page/index.html](assets/landing-page/index.html) and adapt the copy. It already carries the site palette, typography, the mask-frame media treatment and the hairline editorial bands.
- Use a real capture of the tool as the hero media: an actual screenshot, a still, or the product image already on zuravfx.com. Never draw a fake interface in CSS and never leave a placeholder graphic. Capture it yourself when you can.

Read [references/landing-pages.md](references/landing-pages.md) for the design rules, the section structure that works, and what "less AI" means in practice.

## Copy and voice

- UK English, with spelling corrected as you go.
- No em dashes. Use a full stop, comma, colon or brackets instead.
- No emojis.
- Plain, direct and human. Expert and curious, never agency-style self-importance.
- Do not invent credits, client names, prices, licence terms or compatibility claims. If the source material does not say it, it does not go on the page.

## Before you finish

- Confirm the repository name, `origin` URL and target subfolder match the intended destination.
- Confirm the landing page opens with no build step, reads correctly on a narrow viewport, and its download links resolve.
- Confirm the source is backed up, and say where.
