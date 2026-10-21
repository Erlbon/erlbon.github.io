# erlbon.github.io

Source for [erlbon.github.io](https://erlbon.github.io/), the landing site for Erlbon's free, open-source programs:

- [Dossier](https://erlbon.github.io/dossier/) — a dual-pane file manager for Windows — [source](https://github.com/Erlbon/dossier)
- [The Redactor Tools](https://erlbon.github.io/redactors/) — four metadata-editing apps:
  - [The ƆBZ Redactor](https://erlbon.github.io/cbzredactor/) — [source](https://github.com/Erlbon/cbzredactor)
  - [The ƎPUB Redactor](https://erlbon.github.io/epubredactor/) — [source](https://github.com/Erlbon/epubredactor)
  - [The ɯP3 Redactor](https://erlbon.github.io/mp3redactor/) — [source](https://github.com/Erlbon/mp3redactor)
  - [The Ʌideo Redactor](https://erlbon.github.io/videoredactor/) — [source](https://github.com/Erlbon/videoredactor)
- [Pluteus](https://erlbon.github.io/pluteus/) — a light book, comic and music server — [source](https://github.com/Erlbon/pluteus)

Plain static HTML/CSS, no build step — served as-is by GitHub Pages from `main`. The front page (`/index.html`) is a short intro with one card
per project; the Redactor family has its own hub (`/redactors/`); every program has its own page (`/<name>/index.html`); the stylesheet is
`assets/style.css`. Icons are copied in from each project's own repository; update them here if a project's icon changes.

## Updating a page

Just edit the relevant `index.html` and push to `main` — Pages redeploys automatically within a minute or two. A new project: a folder +
`index.html` (copy `dossier/index.html` as the template), a card on the front page, a pill in the "More from Erlbon" lists, and a `<url>` in
`sitemap.xml`. See `CLAUDE.md` for the conventions.
