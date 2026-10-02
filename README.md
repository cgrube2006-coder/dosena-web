# Dosena – Website

Stand: **14.09.2026**. Statische Website im bestehenden Repository
[dosena-web](https://github.com/cgrube2006-coder/dosena-web), Branch `main`.
Letzter Website-Code-Commit: `bffafdb` vom 27.08.2026.
Domain laut `CNAME`: **dosena.de**. Hosting/DNS wurden heute nicht neu geprüft.

## Vorhanden

- `index.html`, `styles.css`, `app.js`: Landingpage.
- `fonts/`: lokal eingebundene Schriften Fraunces und Outfit (variable WOFF2, SIL OFL 1.1).
  Keine Schriften oder andere Ressourcen von Google Fonts/CDNs einbinden (DSGVO, siehe unten).
- `datenschutz.html`, `impressum.html`: vorhandene rechtliche Seiten.
- `app/index.html`: Smart Link für Store-Weiterleitung.
- `CNAME`: bestehende eigene Domain; nicht bei einem Dokumentationsupdate ersetzen.

Die früheren README-Schritte „neues Repo anlegen“ und „erste Dateien hochladen“
waren Erstsetup-Anweisungen und sind für dieses bestehende Projekt nicht mehr aktuell.

## Smart Link

[dosena.de/app](https://dosena.de/app) erkennt im Quellcode Android, iOS/iPadOS oder
Desktop. Mobil wird der passende Store verwendet, am Desktop bleiben Store-Links wählbar.

- Android: [Google Play, com.dosena.app](https://play.google.com/store/apps/details?id=com.dosena.app).
- iOS: [App Store, ID 6783053211](https://apps.apple.com/de/app/dosena-tabletten-erinnerung/id6783053211).
- Übernommene Parameter: `utm_source`, `utm_medium`, `utm_campaign`, `utm_content`, `utm_term`.
- Android bündelt UTM-Werte im `referrer`; iOS setzt `ct` aus Kampagne/Quelle und `mt=8`.

Diese Weitergabe beweist **keine vollständige Installations- oder Kaufattribution**.
Insbesondere unbekannte Quellen in Google Play nicht automatisch Meta zuordnen.

## Übergabe und Pflege

Die App-Quellen liegen separat:
[Android](https://github.com/cgrube2006-coder/MedizinAppAndroid) und
[iOS](https://github.com/cgrube2006-coder/MedizinAppIOS).

Gemeinsame Entscheidungen und die datierte Marketing-Auswertung sind im
[Projektstand](https://github.com/cgrube2006-coder/MedizinAppAndroid/blob/main/docs/projektstand.md)
und [Marketing-Dokument](https://github.com/cgrube2006-coder/MedizinAppAndroid/blob/main/docs/marketing.md)
des Android-Repositories dokumentiert. Zugriff auf diese Repositories kann erforderlich sein.
Keine internen Kontozugangsdaten oder vertraulichen Kampagnendaten in dieses öffentliche Web-Repo kopieren.

## Bei späteren Website-Änderungen

- Nur den beauftragten Inhalt ändern; Domain, Rechtstexte und Store-Ziele nicht beiläufig ersetzen.
- Landingpage mobil/desktop, Store-Links und `/app` mit/ohne UTM prüfen.
- Vor einer Hosting-Änderung die bestehende Konfiguration in GitHub Pages prüfen.
- Quellcode-Push und tatsächliches Deployment getrennt verifizieren.
- README um Änderung, Prüfdatum, Ergebnis und offene Punkte ergänzen.

Diese Pflege ändert nur Dokumentation, keine Website-Funktion und keine Hosting-Einstellung.

## Änderung 01.10.2026: ehrliche Erinnerungstexte

Grund: Eine Compliance-Prüfung fand absolute Aussagen zur Zuverlässigkeit der
Erinnerungen und einen für iOS unzutreffenden Vollbild-Hinweis.

- `index.html`: Meta-Description, Hero-Lead, Badge „Erinnerungen zur festen Uhrzeit“,
  Funktions- und Schritttexte ohne „zuverlässig“/„pünktlich“, Vollbild als Android-Funktion
  gekennzeichnet, FAQ „Wie verlässlich sind die Erinnerungen?“ mit Voraussetzungen.
- `datenschutz.html`: exakte Alarme als Android-Berechtigung gekennzeichnet.
- `impressum.html`: Funktionshinweis zur Zustellung im Haftungshinweis.

Geprüft: Textsuche nach „zuverlässig“, „nie wieder“, „jede Einnahme“, „Vollbild“,
„pünktlich“ (nur noch der gekennzeichnete Android-Vollbild-Satz). Kein JSON-LD/FAQPage-
Schema und keine og:/twitter:-Tags vorhanden. Kein Browser-Rendering-Test.
Offen: Merge des PRs und Kontrolle des GitHub-Pages-Deployments.

## Änderung 01.10.2026: lokale Schriften, Datenschutz für die Website

Grund: `styles.css` lud Fraunces/Outfit per `@import` von fonts.googleapis.com; dabei geht die
IP-Adresse der Besucher ohne Einwilligung an Google (LG München I, 20.01.2022, 3 O 17493/20).
Die Datenschutzerklärung beschrieb nur die App, nicht die Website.

- `fonts/`: variable WOFF2 (Fraunces opsz 9–144/wght 400–700, Outfit wght 300–700; je latin und
  latin-ext) von Google Fonts heruntergeladen, dazu die OFL-Lizenztexte.
- `styles.css`: Google-Import durch `@font-face` mit `font-display: swap` ersetzt; Abstand
  zwischen aufeinanderfolgenden Absätzen in `.legal-card`.
- `datenschutz.html`: neuer Abschnitt 3 „Diese Website“ (GitHub Pages/Server-Logs, DPF,
  keine Cookies/Tracker, lokale Schriften, Smart Link inkl. UTM-Weitergabe, E-Mail-Kontakt),
  Widerspruchsrecht nach Art. 21, BayLDA, Abschnitte neu nummeriert (4–13), Stand Oktober 2026.

Geprüft (lokal, `python -m http.server`): index, datenschutz, impressum-Stil, `/app/` laden nur
eigene Dateien plus eine Inline-`data:`-SVG; `fraunces-latin.woff2`/`outfit-latin.woff2` mit
Status 200, `document.fonts` „loaded“; Gewichts- und opsz-Achsen wirken (Laufweiten ändern sich).
Faktenaussagen zu GitHub (IP-Logging, Adresse, DPF) vom compliance-checker gegen die GitHub-Doku geprüft.
Offen: Merge des PRs, Kontrolle des Pages-Deployments live (Network-Tab ohne Google-Request),
DPF-Eintrag von GitHub einmal manuell unter dataprivacyframework.gov/list prüfen.
Hinweis: `.hero h1 .accent` ist wie zuvor synthetisches Kursiv (Google lieferte auch kein Italic).
