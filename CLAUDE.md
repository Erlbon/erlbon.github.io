# erlbon.github.io

Public landing/SEO site for Erlbon's projects: **Dossier** (a file manager), the **Redactor family** (cbzredactor, epubredactor, mp3redactor, videoredactor) and **Pluteus** (a library server). Plain static HTML/CSS, no build step, no JS framework — GitHub Pages serves it as-is from `main`. The front page is generic (a short intro and one card per project); the Redactor family has its own hub at `/redactors/`; every app has its own sub-page.

## Commands
- Preview: open `index.html` (or any `<app>/index.html`) directly in a browser; no server/build needed
- Deploy: `git push` to `main` — Pages redeploys within a minute or two, no manual step

## Layout
`index.html` (the generic front page), `dossier/`, `pluteus/` (+ `pluteus/compare/`), `redactors/` (the Redactor family hub: formats, what the four share, sources, data licences), `cbzredactor/`, `epubredactor/`, `mp3redactor/`, `videoredactor/`, `databases/` (each its own `index.html`), `assets/style.css`, `assets/img/` icons and `screenshots/`, `robots.txt`, `sitemap.xml`. The site's name in the header is "RIL HUMIN TOOLZ" (the owner's choice, 2026-10-21; plain caps, as written); the author in the JSON-LD stays the GitHub handle, Erlbon.

## Domain notes
- Per-page SEO: unique `<title>`/meta description/canonical link, Open Graph + Twitter card tags, and a JSON-LD `SoftwareApplication` block (name, alternateName, description, url, `downloadUrl` pointing at `.../releases/latest`, operatingSystem, offers price 0, author as `{"@type":"Person","name":"Erlbon","url":"github.com/Erlbon"}` — the GitHub handle, not the user's real name/email).
- Each app's branded name uses a stylized "turned letter" wordmark (e.g. ƆBZ, ƎPUB) that is not plain ASCII — every page also repeats the plain keyword form ("CBZ", "EPUB", "MP3", "video") in title/description/body so text search isn't relying on the glyph alone.
- Dark "redacted document" theme; each app's own brand color (sampled from its icon) is applied per-page via `data-app="cbz|epub|mp3|video"` on `<body>` and CSS custom properties.
- This content is hand-written summary copy, not generated from each app's README — it does not auto-update when an app changes and can drift.
- Each app's `assets/icon.png` is copied in by hand from that app's own repo, not referenced live — recopy it here if an app's icon changes.
- To add a new project: a new folder + `index.html` (copy `dossier/index.html` or `pluteus/index.html` as the template for a program that is not a Redactor), a card on the front page, a pill in the "More from Erlbon" lists of the other pages, and a `<url>` in `sitemap.xml`. To add a Redactor: copy a Redactor sub-page, add a card and a table row on `redactors/index.html`, and the sibling pills on the other Redactor pages.
- Update a project's page when that project is **released** (versions, download, what it can do), not during feature work; verify every claim against the project's own README and release notes.
- Dossier screenshots are made from sample folders and a made-up Home page (no real drives, servers or devices): regenerate them from a Dossier checkout with a script that sets up sample data, never from a real profile.

## Family conventions that apply here
- **Sync first** (see below) — other sessions may edit this repo too.
- **Landing page honesty** — the Formats/feature claims on each app's page must match that app's real menu actions and file-picker filters, not what the underlying library could theoretically do. This has been wrong in both directions before (a claimed capability that was never wired into the GUI; a real shipped feature not yet reflected here). Verify against the app's own repo before describing what it does.
- Version-bump, progress-feedback, promote-to-redactor_common, and cross-platform rules don't apply to this repo (no `APP_VERSION`, no per-book loops, no shared library dependency, not a desktop app).

### Sync first
Other Claude sessions, sometimes on other machines, edit these repos concurrently. Before editing, and again right before every `git push`: `git fetch origin -q; git status --porcelain -b`. Confirm you match origin and the tree is clean. Fast-forward if behind; resolve if diverged.

Full family conventions: `.claude/skills/redactor-conventions/SKILL.md` in [redactor_common](https://github.com/Erlbon/redactor_common).
