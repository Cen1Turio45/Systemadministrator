# Gruppenrichtlinien prüfen mit gpresult

## Ziel

Diese Anleitung beschreibt, wie aktive Gruppenrichtlinien geprüft und dokumentiert werden.

## GPOs in der Konsole prüfen

1. `Group Policy Management` öffnen.
2. Domäne auswählen.
3. Relevante OU oder Policy öffnen.
4. Tab `Settings` prüfen.
5. Einstellungen und Verknüpfungen dokumentieren.

## gpresult-Bericht erstellen

Auf einem domänenverbundenen Client eine administrative Eingabeaufforderung öffnen:

```cmd
gpresult /h C:\gpresult.html
```

Danach die Datei öffnen:

```text
C:\gpresult.html
```

## Wann gpresult hilfreich ist

- Benutzer erhält eine Einstellung nicht.
- Computer bekommt eine Policy nicht.
- Mehrere GPOs überschneiden sich.
- Loopback Processing ist aktiv.
- Es ist unklar, welche Policy gewinnt.

## Wichtige Prüfpunkte

- angewendete Benutzer-GPOs
- angewendete Computer-GPOs
- gefilterte oder abgelehnte GPOs
- Sicherheitsfilterung
- WMI-Filter
- OU-Pfad des Benutzers oder Computers

## GPO aktualisieren

```cmd
gpupdate /force
```

Danach je nach Policy abmelden, neu anmelden oder neu starten.

## Dokumentation im Ticket

Festhalten:

- Gerät
- Benutzer
- betroffene Einstellung
- erwartetes Verhalten
- angewendete GPOs
- Ergebnis von `gpresult`
