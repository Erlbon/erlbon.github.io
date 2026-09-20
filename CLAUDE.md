# erlbon.github.io

Public landing/SEO site for the Redactor family (cbzredactor, epubredactor, mp3redactor, videoredactor). Plain static HTML/CSS, no build step, no JS framework — GitHub Pages serves it as-is from `main`. Each app has its own sub-page plus a shared hub.

## Commands
- Preview: open `index.html` (or any `<app>/index.html`) directly in a browser; no server/build needed
- Deploy: `git push` to `main` — Pages redeploys within a minute or two, no manual step

## Layout
`index.html` (hub), `cbzredactor/`, `epubredactor/`, `mp3redactor/`, `videoredactor/` (each its own `index.html`), `assets/style.css`, `assets/` icons, `robots.txt`, `sitemap.xml`.

## Domain notes
- Per-page SEO: unique `<title>`/meta description/canonical link, Open Graph + Twitter card tags, and a JSON-LD `SoftwareApplication` block (name, alternateName, description, url, `downloadUrl` pointing at `.../releases/latest`, operatingSystem, offers price 0, author as `{"@type":"Person","name":"Erlbon","url":"github.com/Erlbon"}` — the GitHub handle, not the user's real name/email).
- Each app's branded name uses a stylized "turned letter" wordmark (e.g. ƆBZ, ƎPUB) that is not plain ASCII — every page also repeats the plain keyword form ("CBZ", "EPUB", "MP3", "video") in title/description/body so text search isn't relying on the glyph alone.
- Dark "redacted document" theme; each app's own brand color (sampled from its icon) is applied per-page via `data-app="cbz|epub|mp3|video"` on `<body>` and CSS custom properties.
- This content is hand-written summary copy, not generated from each app's README — it does not auto-update when an app changes and can drift.
- Each app's `assets/icon.png` is copied in by hand from that app's own repo, not referenced live — recopy it here if an app's icon changes.
- To add a new app: a new folder + `index.html` (copy an existing sub-page as a template), a card on the hub, an entry in every sibling page's "rest of the family" list, and a `<url>` in `sitemap.xml`.

## Family conventions that apply here
- **Sync first** (see below) — other sessions may edit this repo too.
- **Landing page honesty** — the Formats/feature claims on each app's page must match that app's real menu actions and file-picker filters, not what the underlying library could theoretically do. This has been wrong in both directions before (a claimed capability that was never wired into the GUI; a real shipped feature not yet reflected here). Verify against the app's own repo before describing what it does.
- Version-bump, progress-feedback, promote-to-redactor_common, and cross-platform rules don't apply to this repo (no `APP_VERSION`, no per-book loops, no shared library dependency, not a desktop app).

### Sync first
Other Claude sessions, sometimes on other machines, edit these repos concurrently. Before editing, and again right before every `git push`: `git fetch origin -q; git status --porcelain -b`. Confirm you match origin and the tree is clean. Fast-forward if behind; resolve if diverged.

Full family conventions: `.claude/skills/redactor-conventions/SKILL.md` in [redactor_common](https://github.com/Erlbon/redactor_common).
