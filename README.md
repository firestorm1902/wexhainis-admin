# Wexhainis Verwaltung

Dashboard nur für den Super-Admin: alle Mitgliederkonten und Rechte von **Getränke-Strichliste** und **Wexhainer Stundentracker** an einem Ort.
Läuft auf GitHub Pages und nutzt dasselbe Firebase-Projekt (`wexhainis-getraenkestrichliste`) wie die beiden Apps.

Adresse: https://firestorm1902.github.io/wexhainis-admin/

## Bereiche
- **Übersicht** – Kennzahlen beider Apps und eine Liste mit allem, was zu erledigen ist (Anmeldungen, Löschanträge, Nachrichten, Anträge, Rechte-Hinweise)
- **Mitglieder** – alle Profile mit Filter und Suche; Gruppe, Strichliste-Rolle, Jugendschutz, Stundentracker-Freigabe und Stunden-Rolle direkt in der Tabelle ändern; Mehrfachauswahl; Excel-Export; Detailansicht mit Sperren, Entfernen, Wiederherstellen, Umbenennen
- **Rechte** – wer darf was in welcher App, plus automatische Hinweise auf Widersprüche
- **Pflichtstunden** – Ist/Soll je Mitglied und Jahr, Rechnungsstatus, Excel-Export
- **Posteingang** – Nachrichten beantworten und erledigen, offene Korrekturanträge ansehen
- **Protokoll** – die letzten 400 Einträge, durchsuchbar
- **Links & Hilfe** – Apps, Repos, Firebase-Konsole

## Sicherheit
Die Seite ist öffentlich erreichbar, die Daten aber nicht: Lesen und Schreiben erlauben die Firestore-Regeln nur Nutzer-IDs in `superUids()`.
Andere Konten sehen nach der Anmeldung nur „Kein Zugriff“. Es sind keine Regeländerungen nötig – die Regeln aus dem Stundentracker-Repo decken alles ab.

## Bewusst nicht hier
- Buchungen löschen (auch bei Löschanträgen) und Korrekturanträge entscheiden → Strichliste (dort werden Tageszähler neu berechnet)
- Erinnerungen, Rechnungen, individuelles Soll → Stundentracker
- Firebase-Logins löschen, Passwort-Reset → Firebase-Konsole, Authentication

Änderungen aus der Verwaltung landen im Protokoll mit dem Präfix `[Verwaltung]`.
