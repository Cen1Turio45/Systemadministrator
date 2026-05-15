# File-Shares und Berechtigungen

## Ziel

Diese Anleitung beschreibt, wie File-Shares erstellt, Berechtigungen geprüft und Benutzer über Gruppen berechtigt werden.

## Grundprinzip

Zugriffe auf Freigaben sollten über Gruppen gesteuert werden. Das ist sauberer, nachvollziehbarer und einfacher zu pflegen.

## Share erstellen

1. Auf dem Fileserver einen Ordner erstellen.
2. Eigenschaften des Ordners öffnen.
3. Tab `Freigabe` öffnen.
4. `Erweiterte Freigabe` auswählen.
5. `Diesen Ordner freigeben` aktivieren.
6. Freigabename vergeben.
7. Berechtigungen setzen.

## Zugriff testen

Auf einem Client im Explorer öffnen:

```text
\\SERVERNAME\Freigabename
```

Beispiel:

```text
\\dc01\file
```

## Berechtigungen prüfen

1. Server Manager öffnen.
2. `File and Storage Services > Shares` öffnen.
3. Freigabe auswählen.
4. Eigenschaften öffnen.
5. `Permissions` prüfen.
6. `Effective Access` verwenden, um den tatsächlichen Zugriff eines Benutzers zu prüfen.

## Benutzer berechtigen

1. In Active Directory die passende Berechtigungsgruppe suchen.
2. Benutzer zur Gruppe hinzufügen.
3. Änderung übernehmen.
4. Benutzer abmelden oder Computer neu starten lassen, damit Gruppentoken aktualisiert werden.
5. Zugriff erneut testen.

## Typische Fehler

| Problem | Mögliche Ursache |
| --- | --- |
| Benutzer sieht Share nicht | falscher Pfad, DNS-Problem, keine Berechtigung |
| Zugriff verweigert | NTFS- oder Share-Berechtigung fehlt |
| Zugriff klappt nach Gruppenänderung nicht | Benutzer muss sich neu anmelden |
| Nur Lesen statt Schreiben | Berechtigung auf Share oder NTFS zu niedrig |

## Dokumentation im Ticket

Festhalten:

- Share-Pfad
- betroffener Benutzer
- hinzugefügte Gruppe
- getestetes Ergebnis
- Zeitpunkt der Änderung
