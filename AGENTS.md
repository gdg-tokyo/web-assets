# AGENTS — Assistant instructions for gdg-tokyo/web-assets

Purpose
- Help AI coding agents understand repository intent and safe edits.

Quick facts
- Hosting: images are served from `https://gdg-tokyo.github.io/web-assets/` via GitHub Pages. See [README.md](README.md).
- No build/test: This repo contains static image assets; there is no build or test command.
- Important paths: `events/` (event-scoped assets), `speakers/` (reusable speaker images). See [README.md](README.md#%E3%83%86%E3%82%99%E3%82%A3%E3%83%AC%E3%82%AF%E3%83%88%E3%83%AA%E6%A7%8B%E6%88%90).

Conventions agents must follow
- Do not modify binary assets without an explicit user instruction and a PR description.
- When proposing file additions, follow naming conventions: append upload date as `-YYYYMMDD` (see README).
- Avoid large or lossy re-encodings; if optimizing images, include original copies and document changes in the PR.
- For metadata or content changes (e.g., speaker name or event date), propose a PR and include the URLs that will be affected.

Suggested agent tasks
- Validate new image filenames and path placement according to `README.md` rules.
- Detect obvious duplicates or near-duplicates and surface recommendations (don't delete without consent).
- Suggest lightweight optimizations (lossless) and produce a PR with both originals and optimized files.

Where to look
- Primary documentation: [README.md](README.md)
- Key directories: `events/`, `speakers/`

Next steps (optional)
- Create a repository skill to run filename/path linting and produce a report: `/create-skill filename-lint`
- Add an automated PR template that reminds contributors to include the upload date suffix.

Examples
- Filename lint rule: filenames under `speakers/` must match `/^[a-z0-9-]+-\d{8}\.(png|jpg|jpeg)$/i` and include the upload date suffix.
- Path placement rule: one-off event speaker photos go into `events/[year]/[date-eventname]/` not `speakers/`.
- Optimization example command (for human review): `pngcrush -brute src.png out.png` — include both `src.png` and `out.png` in the PR.

