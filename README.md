# konolfstudio.app

Öffentliche Seiten zu Jans Apps, ausgeliefert über GitHub Pages (Branch `main`, Ordner `/`):
https://jnd1992.github.io/konolfstudio.app/

## Aufbau

```
index.html                         Startseite (Links)
datenschutz/
  index.html                       Übersicht aller Datenschutzerklärungen
  magic-brawl-odyssey/
    index.html                     Datenschutzerklärung „Magic Brawl Odyssey“
.nojekyll                          GitHub Pages liefert die Dateien unverändert aus
```

Jede App bekommt unter `datenschutz/` einen eigenen Ordner mit einer `index.html`. Die Adresse ist dann
`https://jnd1992.github.io/konolfstudio.app/datenschutz/<ordner>/`. Neue App: Ordner anlegen und in
`datenschutz/index.html` verlinken. Ordnernamen nie umbenennen – die Adresse steht in den Apps und in der Play Console.

## Magic Brawl Odyssey

- Adresse: https://jnd1992.github.io/konolfstudio.app/datenschutz/magic-brawl-odyssey/
  (Löschung: `#loeschung`, Kontakt: `#kontakt`)
- Quelle im Spielprojekt: `Docs/Koop/Legal/datenschutz.html` (JND1992/magicbrawlodyssey) – Änderungen dort und hier
  gleich halten.
- Im Spiel: `GameLinks.PrivacyUrl`. Bis 10.10.2026 lag die Erklärung unter
  https://jnd1992.github.io/magicbrawlodyssey-legal/datenschutz.html (App-Versionen bis 1.0.7 öffnen sie; eine Weiterleitung
  hierher ist vorbereitet und geht nach Jans OK online, nachdem die Play Console auf die neue Adresse umgestellt ist).

## Eigene Domain (optional)

Soll die Seite unter `https://konolfstudio.app/` erscheinen: in Cloudflare die DNS-Einträge für GitHub Pages anlegen
(nur DNS, ohne Proxy – sonst verarbeitet auch Cloudflare die Aufrufe, und Abschnitt 12 der Erklärungen müsste das
nennen), dann unter *Settings › Pages › Custom domain* `konolfstudio.app` eintragen und „Enforce HTTPS“ anhaken.
Die `jnd1992.github.io/konolfstudio.app/...`-Adressen leiten danach automatisch weiter.
