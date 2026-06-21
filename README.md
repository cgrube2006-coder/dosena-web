# Dosena – Website (Datenschutz & Impressum)

Diese Seite wird **öffentlich** gehostet, damit die App-Stores die Datenschutz-URL
prüfen können. Empfehlung: **GitHub Pages** (kostenlos).

## Schritt 1 – Platzhalter ausfüllen (Pflicht)
In `datenschutz.html` und `impressum.html` alle `[...]`-Platzhalter ersetzen:
- `[DEIN NAME]`, `[STRASSE NR.]`, `[PLZ ORT]`, `[DEINE E-MAIL]`, `[DATUM EINTRAGEN]`

> Hinweis: In Deutschland sind Impressum + Datenschutzerklärung Pflicht, inkl.
> ladungsfähiger Anschrift. Wenn du deine Privatadresse nicht öffentlich zeigen willst,
> ist das ein guter Zeitpunkt, dich kurz zu informieren (z. B. Zustelldienst-Adresse).
> Diese Vorlage ist ein solider Start, aber keine Rechtsberatung.

## Schritt 2 – Öffentliches Repo anlegen
1. Auf github.com → **New repository**
2. Name z. B. `medibegleiter-web`, **Public** (wichtig!), ohne README
3. Erstellen

## Schritt 3 – Dateien hochladen
Am einfachsten über die Weboberfläche: im neuen Repo **„Add file → Upload files"**,
dann **alle** Dateien aus diesem `website/`-Ordner hochladen und committen:
- `index.html`, `datenschutz.html`, `impressum.html`
- `styles.css`, `app.js`  ← wichtig, sonst fehlt das Design!

(Oder per Terminal: in diesem `website/`-Ordner `git init`, committen,
`git remote add origin <URL>`, `git push`.)

> Tipp zum Vorschauen: Du kannst `index.html` auch einfach lokal per Doppelklick im
> Browser öffnen, um die Seite vorab anzusehen.

## Schritt 4 – GitHub Pages aktivieren
1. Im Repo: **Settings → Pages**
2. Source: **Deploy from a branch**, Branch: **main**, Ordner: **/(root)** → Save
3. Nach 1–2 Minuten erscheint oben die URL, z. B.
   `https://cgrube2006-coder.github.io/medibegleiter-web/`

## Schritt 5 – URLs notieren (für die Stores & die App)
- Datenschutz: `https://<dein-pages-link>/datenschutz.html`
- Impressum:  `https://<dein-pages-link>/impressum.html`

Diese Datenschutz-URL trägst du später ein:
- **Google Play Console** → App-Inhalte → Datenschutzerklärung
- **App Store Connect** → App-Datenschutz → Datenschutzrichtlinien-URL

Sag mir die Datenschutz-URL – dann verlinke ich sie auch direkt in der App.
