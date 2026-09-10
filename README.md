# erlbon.github.io

Source for [The Redactor Tools](https://erlbon.github.io/), the landing site
for the "Redactor" family of free, open-source Windows metadata-editing
apps:

- [The ƆBZ Redactor](https://erlbon.github.io/cbzredactor/) — [source](https://github.com/Erlbon/cbzredactor)
- [The ƎPUB Redactor](https://erlbon.github.io/epubredactor/) — [source](https://github.com/Erlbon/epubredactor)
- [The ɯP3 Redactor](https://erlbon.github.io/mp3redactor/) — [source](https://github.com/Erlbon/mp3redactor)
- [The Ʌideo Redactor](https://erlbon.github.io/videoredactor/) — [source](https://github.com/Erlbon/videoredactor)

Plain static HTML/CSS, no build step — served as-is by GitHub Pages from
`main`. Each app gets its own page (`/<app>/index.html`) plus a shared hub
(`/index.html`) and stylesheet (`assets/style.css`). App icons are copied in
from each app's own `assets/icon.png`; update them here if an app's icon
changes.

## Updating a page

Just edit the relevant `index.html` and push to `main` — Pages redeploys
automatically within a minute or two. If a new app joins the family, add a
folder + `index.html` for it, a card on the hub page, an entry in each
sibling page's "rest of the family" list, and a `<url>` in `sitemap.xml`.
