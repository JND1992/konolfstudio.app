# konolfstudio.app

Öffentliche Seiten zu Jans Apps, ausgeliefert über GitHub Pages (Branch `main`, Ordner `/`):
https://jnd1992.github.io/konolfstudio.app/

## Aufbau

```
index.html                         Startseite (Links)
datenschutz/
  index.html                       Übersicht aller Datenschutzerklärungen
  fuzzy-meadow/
    index.html                     Datenschutzerklärung „Fuzzy Meadow“
  magic-brawl-odyssey/
    index.html                     Datenschutzerklärung „Magic Brawl Odyssey“
  little-farmstand/
    index.html                     Datenschutzerklärung „Little Farmstand“
lizenzen/
  magic-brawl-odyssey/
    index.html                     Open-Source-Lizenzen „Magic Brawl Odyssey“ (erzeugt, nicht von Hand ändern)
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
  https://jnd1992.github.io/magicbrawlodyssey-legal/datenschutz.html (App-Versionen bis 1.0.7 öffnen sie; sie leitet seit
  11.10.2026 hierher weiter).

### Open-Source-Lizenzen (Magic Brawl Odyssey)

- Adresse: https://jnd1992.github.io/konolfstudio.app/lizenzen/magic-brawl-odyssey/ (im Spiel: `GameLinks.LicensesUrl`,
  Knopf „Website öffnen“ im Fenster EINSTELLUNGEN › Online & Info › Open-Source-Lizenzen). Verlinkt von `index.html`.
- Die Seite wird **erzeugt** – nicht von Hand ändern. Das Skript `Tools/Legal/build_notices.py` im Spielprojekt
  (JND1992/magicbrawlodyssey) schreibt sie zusammen mit demselben Text für die App
  (`Assets/Resources/Legal/OpenSourceLicenses.txt`), aus dem gebauten AAB, dem Gradle-Cache, `Library/PackageCache` und
  dem NDK. Neu erzeugen (im Spielprojekt, dieses Repo liegt daneben):
  ```
  python Tools/Legal/build_notices.py            # schreibt beide Dateien
  python Tools/Legal/build_notices.py --check    # schreibt nichts; Exit-Code 1, wenn eine Datei veraltet ist
                                                 # (CRLF aus dem git-Checkout zählt nicht als Änderung)
  ```
  Danach beide Repos committen. Nötig nach jedem SDK- oder Paket-Update (Release-Checkliste des Spiels, Punkt 3.8).
- Keine Skripte, keine Cookies; große Lizenztexte sind eingeklappt (`<details>`), alles andere ist sichtbar.

## Fuzzy Meadow

- Adresse: https://jnd1992.github.io/konolfstudio.app/datenschutz/fuzzy-meadow/ (Deutsch `#de`, Englisch `#en`)
- Quelle im Spielprojekt: `Docs/Datenschutz/index.html` (Fuzzy Meadow) – Änderungen dort und hier gleich halten.
- Die App sammelt keine Daten und hat keine Internet-Berechtigung. Wird der Kauf der Vollversion (Google Play Billing)
  scharf geschaltet, braucht die App Internet – dann die Erklärung prüfen (Abschnitt 5 nennt den Kauf schon).

## Little Farmstand

- Adresse: https://konolfstudio.app/datenschutz/little-farmstand/ (Deutsch `#de`, Englisch `#en`)
- Quelle im Spielprojekt: `Docs/Store/datenschutz.html` (JND1992/LittleFarmstand) – Änderungen dort und hier gleich halten.
- Die App sammelt keine Daten, hat keine Werbung, keine Käufe und keine Internet-Berechtigung
  (wird beim Build per `Assets/Game/Editor/ManifestFix.cs` entfernt).

## Eigene Domain (optional)

Soll die Seite unter `https://konolfstudio.app/` erscheinen: in Cloudflare die DNS-Einträge für GitHub Pages anlegen
(nur DNS, ohne Proxy – sonst verarbeitet auch Cloudflare die Aufrufe, und Abschnitt 12 der Erklärungen müsste das
nennen), dann unter *Settings › Pages › Custom domain* `konolfstudio.app` eintragen und „Enforce HTTPS“ anhaken.
Die `jnd1992.github.io/konolfstudio.app/...`-Adressen leiten danach automatisch weiter.
