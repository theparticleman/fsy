# fsy

A single static page that deep-links into the Gospel Library Android app
(the **For the Strength of Youth** youth study section). It exists so a
non-technical person can save a home-screen shortcut that opens the app
directly instead of the website.

Hosted on GitHub Pages at https://fsy.jonathanandmelinda.com/ — `index.html`
shows a button linking to `https://www.churchofjesuschrist.org/study/youth?lang=eng`,
which Android hands off to Gospel Library.

## Do NOT add a web manifest

This repo intentionally has **no** web manifest (`manifest.json` /
`site.webmanifest`), and it must stay that way.

A manifest makes Android/Chrome offer **"Install"** (PWA mode) instead of
**"Add to Home screen"** (a plain shortcut). An installed PWA launches inside
the browser engine's own context, so the church link opens *within* the PWA
instead of being handed off to the Gospel Library app — defeating the entire
purpose of this page.

With no manifest, the browser only offers "Add to Home screen", which routes
the URL through the Android system and lets it deep-link into the app. The
icons are wired up with plain `<link rel="icon">` and
`<link rel="apple-touch-icon">` tags, which need no manifest.
