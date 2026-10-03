# Dosena – Website

Statische Website für [dosena.de](https://dosena.de), ausgeliefert über GitHub Pages
aus dem Branch `main`. Domain laut `CNAME`.

## Aufbau

- `index.html`, `styles.css`, `app.js`: Landingpage.
- `fonts/`: lokal eingebundene Schriften Fraunces und Outfit (variable WOFF2, SIL OFL 1.1).
  Keine Schriften oder andere Ressourcen von Google Fonts oder CDNs einbinden.
- `datenschutz.html`, `impressum.html`: rechtliche Seiten.
- `app/index.html`: Smart Link für die Store-Weiterleitung.
- `media/social/`: Grafiken und Videos für Social-Media-Beiträge (nicht verlinkt, per `robots.txt` von der Indexierung ausgenommen).
- `robots.txt`: schließt `/media/` von Suchmaschinen aus.
- `CNAME`: eigene Domain; nicht bei einem Dokumentationsupdate ersetzen.

## Smart Link

[dosena.de/app](https://dosena.de/app) erkennt Android, iOS/iPadOS oder Desktop.
Mobil wird der passende Store geöffnet, am Desktop bleiben beide Store-Links wählbar.

- Android: [Google Play, com.dosena.app](https://play.google.com/store/apps/details?id=com.dosena.app).
- iOS: [App Store, ID 6783053211](https://apps.apple.com/de/app/dosena-tabletten-erinnerung/id6783053211).
- Übernommene Parameter: `utm_source`, `utm_medium`, `utm_campaign`, `utm_content`, `utm_term`.
- Android bündelt die UTM-Werte im `referrer`; iOS setzt `ct` aus Kampagne/Quelle und `mt=8`.

## Bei Änderungen

- Nur den beauftragten Inhalt ändern; Domain, Rechtstexte und Store-Ziele nicht beiläufig ersetzen.
- Landingpage mobil und am Desktop, Store-Links und `/app` mit und ohne UTM prüfen.
- Vor einer Hosting-Änderung die bestehende Konfiguration in GitHub Pages prüfen.
- Quellcode-Push und tatsächliches Deployment getrennt verifizieren.

Dieses Repository ist öffentlich. Das Änderungsprotokoll mit Prüfergebnissen und offenen
Punkten wird im (privaten) App-Repository geführt.
