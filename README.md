# Dosena – Website

Stand: **14.09.2026**. Statische Website im bestehenden Repository
[dosena-web](https://github.com/cgrube2006-coder/dosena-web), Branch `main`.
Letzter Website-Code-Commit: `bffafdb` vom 27.08.2026.
Domain laut `CNAME`: **dosena.de**. Hosting/DNS wurden heute nicht neu geprüft.

## Vorhanden

- `index.html`, `styles.css`, `app.js`: Landingpage.
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

## Änderung 02.10.2026: System-Backups offengelegt

Grund: Android- und iOS-App lassen die Datensicherung des Betriebssystems (Google-Sicherung,
iCloud-/Computer-Backup) zu. Die Website versprach „100 % lokal“ und erwähnte Backups nicht.

- `datenschutz.html`: neuer Abschnitt 6 „Datensicherung durch dein Betriebssystem“
  (Verschlüsselung, Gerätewechsel, Rolle Google/Apple), Abschnitte 2, 3 und
  „Speicherdauer & Löschung“ angepasst, folgende Abschnitte umnummeriert (jetzt 1–13),
  Änderungshinweis, Stand Oktober 2026.
- `index.html`: Meta-Description, Badges („Kein Konto, kein Dosena-Server“,
  „Ohne Konto, ohne Dosena-Server“), Preisliste „Export & Wiederherstellung (Datei)“, FAQ.

Geprüft: code-reviewer (Querverweise, HTML), compliance-checker. Kein Browser-Rendering-Test.
Offen: Erst mergen, wenn die App-Versionen mit den neuen Texten in den Stores sind.
Vom compliance-checker zusätzlich angemerkt (nicht Teil dieser Änderung): Hosting- (GitHub
Pages) und E-Mail-Kontakt-Abschnitt in der Datenschutzerklärung fehlen; „DSGVO-konform“
als Werbeaussage prüfen.
