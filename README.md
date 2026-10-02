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
als Werbeaussage prüfen. (Erledigt, siehe nächsten Eintrag; die Abschnittsnummern oben
gelten vor dem Zusammenführen mit PR #2.)

## Änderung 02.10.2026: PR #2 und #4 zusammengeführt, „DSGVO-konform“ entfernt

Grund: PR #2 (Hosting/E-Mail-Kontakt in der Datenschutzerklärung) und PR #4 (System-Backups)
nummerierten beide die Abschnitte um und kollidierten. „DSGVO-konform“ ist als Werbeaussage
eine pauschale Selbstzuschreibung ohne Prüfung und daher irreführungsanfällig (UWG).

- Branch `docs/datenschutz-hosting-kontakt` setzt auf PR #4 auf und enthält PR #2 per Merge.
- `datenschutz.html`: Abschnitt 3 „Diese Website“ (aus PR #2) vor den App-Abschnitten,
  Datensicherung jetzt Abschnitt 7, Abschnitte 1–14, Querverweise (7, 8) angepasst.
  Überblick präzisiert: „über die App“ keine personenbezogenen Daten (Support-Mails werden
  verarbeitet, siehe Abschnitt 3). Rechte-Abschnitt nennt E-Mails, Änderungshinweis nennt
  Abschnitte 3 und 7.
- `datenschutz.html` nach compliance-checker: E-Mail-Kontakt mit getrennter Rechtsgrundlage
  (lit. b bei Abo/App, sonst lit. f), Art. 9 Abs. 2 lit. a für freiwillig gesendete
  Gesundheitsangaben samt Widerruf (auch in „Deine Rechte“), Anbieter Google Ireland Limited
  bzw. Google LLC (DPF); Beleglink zum GitHub-IP-Logging; Smart Link: an Apple geht nur der
  Kampagnenname (`ct`), an Google Play alle UTM-Werte (wie in `app/index.html`).
- `index.html`: Hero-Badge „DSGVO-konform“ entfernt („Kein Tracking, keine Werbung“ steht
  dort schon), im Trust-Streifen durch „Kein Tracking, keine Werbung“ ersetzt.

Offen: wie bei PR #4 erst mergen, wenn die App-Versionen mit Backup-Texten in den Stores sind.
Soll der Hosting-Teil früher live gehen, PR #2 zuerst mergen; dieser Branch enthält die
Konfliktauflösung bereits. DPF-Einträge von GitHub und Google manuell unter
dataprivacyframework.gov/list prüfen. Kein Browser-Rendering-Test.
Rechtlich offen (compliance-checker): ob das Senden einer E-Mail als „ausdrückliche“
Einwilligung nach Art. 9 genügt; privates Gmail erlaubt keinen AV-Vertrag (Alternative:
Postfach unter @dosena.de bei einem EU-Anbieter); konkrete Löschfrist für E-Mails festlegen.

## Änderung 02.10.2026: Landingpage ohne Bewertungs- und Wirkungsaussagen

Grund: Der compliance-checker fand in `index.html` Texte, die eine medizinische Bewertung von
Messwerten nahelegen (MDR-Abgrenzung), eine Statistik ohne Quelle (HWG § 3, UWG § 5) und
Aussagen zu Fortschritt bzw. Therapietreue, die die App so nicht misst.

- Mockup: Chip „Blutdruck stabil“ → „Blutdruck eingetragen“ (Puls- statt Trend-Icon), Badges
  „stabil“ und „stark“ entfernt, „93 % Therapietreue“ → „82 % bestätigt / Einnahmen im laufenden
  Monat“ (passt jetzt zu den 18 von 22 grünen Kalendertagen).
- Statistik „50 % vergessen ihre Medikamente regelmäßig*“ samt Fußnote entfernt (keine
  belastbare Quelle, die WHO-Zahl von 2003 betrifft Therapietreue bei Langzeittherapien);
  Kachel ersetzt durch „0 – Tracker und Werbung“ (Datenschutzerklärung Abschnitt 9).
- Texte: „Werte festhalten, Verlauf ansehen“, Diagramme zeigen „deine eingetragenen Werte im
  Zeitverlauf“, „…zeigen dir und deinem Arzt, was du eingetragen hast“, „Deine Einnahmen auf
  einen Blick“, „Offene und ausgelassene Einnahmen erkennen“, „Deine Medikamente organisiert –
  an einem Ort“, „Erinnerungen zur eingestellten Uhrzeit“, CTA „Behalte deine Medikamente im
  Blick.“ / „Starte kostenlos mit Dosena – ganz ohne Konto.“
- FAQ „Wo werden meine Daten gespeichert?“: „können … enthalten sein“, Verschlüsselungs-Hinweis
  mit Link auf Datenschutzerklärung Abschnitt 7, Hinweis auf Kopien in Gerätesicherungen.
- `styles.css`: Links in FAQ-Antworten sichtbar (Teal, unterstrichen).

Branch `fix/compliance-index-texte` setzt auf `docs/datenschutz-hosting-kontakt` (PR #5, auf
PR #4) auf. Mit PR #3 (`fix/gratis-report-texte`) ist im FAQ-Block ein Konflikt zu erwarten
(benachbarte Zeilen), wie schon zwischen PR #3 und PR #4.

Geprüft: compliance-checker (erst Funde K2/K3/E6/E7, dann Nachprüfung: nichts Kritisches oder
Hohes mehr, mittlere Funde zu „Therapietreue/dranbleiben“ übernommen); Textsuche nach
„Therapietreue“, „dranzubleiben“, „stabil“, „Trends“, „festen Uhrzeit“ ohne Treffer;
`<div>`/`<a>` ausgeglichen; Android-Build (Gradle-Dateien) und iOS-Projekt (`project.yml`)
ohne Tracking-/Crash-SDKs.
Kein Browser-Rendering-Test.
Offen (niedrig, compliance-checker): „Dein Gesundheits-Begleiter“, „Smarte Erinnerungen“,
„Verlauf & Treue“/„Plan, Treue und Werte“ (kollidiert mit PR #3), „Der solide Start in deine
Therapie“, „Werte-Tracking“ neben „Kein Tracking“, „organisiert und dokumentiert deine
Therapie“ im Disclaimer, PAngV-Hinweis (inkl. MwSt., Abo-Verlängerung) bei den Preisen.
