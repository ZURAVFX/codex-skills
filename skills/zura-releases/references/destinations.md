# Destinations

Exact locations for each part of a release. Before committing, verify the repository root, the `origin` URL and the intended subfolder. Local directory names and old chat links are not authoritative when they conflict with this.

## Public releases

Repository: `ZURAVFX/<Project>`, public. Where a landing page is used, GitHub Pages serves `docs/` from `main`.

Website roll-out, in the `ZURAVFX/portfolio` repository:

- Add the tool to the `tools` array in `src/data/site.json`.
- Put the catalogue image in `public/products/` and reference it as `/products/<file>`.
- A local checkout usually exists at `C:\Users\ellio\Documents\portfolio website`.
- Verified before publishing with `npm run check` and then `npm run build`.
- Hosted on Cloudflare Pages: production branch `main`, build command `npm run build`, output directory `dist`.
- The Gumroad shelf is refreshed by a scheduled workflow that preserves curated display names, descriptions, categories, order and thumbnails. Edit those deliberately rather than letting a sync overwrite them.
- Do not put the Gumroad token in the browser, in `.env.example`, or in any committed file.

`ZURAVFX/ZURA-OCIO-Look` is a working example of the pattern: Pages from `docs/`, a single `index.html`, assets in `dist/`.

## Private releases

Repository: `OA-Motion/OA_Motion_Software_Plugins`, private.

- `software/` holds built installers and distribution archives, for example `Motion-Studio-Setup-1.2.1.exe` or `RenderLift-v0.5.0-Windows-x64.zip`. Source does not belong here.
- `Blender/`, `After-effects/`, `C4D/` and `Davinci-Resolve/` hold per-software source and tools.
- The README lists what is available and how to install it. Because the repository is private, installing from it needs GitHub access to the `OA-Motion` organisation.

## Source backup

Repository: `OA-Motion/project_development_files`, private monorepo, one folder per project, existing history preserved.

Rules already recorded in that repository:

- Work inside the project's own folder, for example `RenderLift-Studio/`.
- Push source and development commits there. Legacy per-project backup repositories are not active development destinations: do not recreate, unarchive or push new development to them without an explicit instruction.
- Do not replace the repository root with a standalone checkout of one project, and do not force-push unrelated history.
- Namespace tags per project, for example `renderlift/v0.3.0`.
- Keep imported third-party and vendor runtimes, credentials, local sessions, generated exports and installed dependencies out of Git, and respect each project's ignore rules.
- Preserve historical backups. Do not delete a legacy repository just to tidy up.

## Safety

- No force pushes to shared history.
- Do not delete or archive repositories without an explicit instruction.
- Keep client assets, tokens and `.env` files out of every public repository.
