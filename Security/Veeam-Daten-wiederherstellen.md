# Daten mit Veeam wiederherstellen

## Ziel

Diese Anleitung beschreibt die Wiederherstellung einzelner Daten oder E-Mail-Elemente aus einem Veeam-Backup.

## Vorbereitung

Vor der Wiederherstellung prüfen:

- Welche Daten sollen wiederhergestellt werden?
- Welcher Benutzer oder welches Postfach ist betroffen?
- Von welchem Zeitpunkt soll wiederhergestellt werden?
- Ist der gewünschte Wiederherstellungspunkt noch verfügbar?
- Gibt es eine Freigabe zur Wiederherstellung?

## Vorgehen

1. Veeam Backup Server öffnen.
2. `Restore` auswählen.
3. Passenden Restore-Typ auswählen, z. B. Anwendungselemente.
4. Gewünschtes Backup auswählen.
5. Postfach oder Datenquelle auswählen.
6. Gesuchte Datei oder E-Mail suchen.
7. Wiederherstellung durchführen.
8. Ergebnis prüfen.

## Hinweis zur Aufbewahrung

Wiederherstellungen sind nur innerhalb der vorhandenen Aufbewahrungszeit möglich. Wenn Backups nur für einen begrenzten Zeitraum gespeichert werden, sind ältere Daten eventuell nicht mehr verfügbar.

## Dokumentation im Ticket

Festhalten:

- betroffener Benutzer
- wiederhergestellte Daten
- Wiederherstellungszeitpunkt
- Restore-Punkt
- Ziel der Wiederherstellung
- Ergebnis
