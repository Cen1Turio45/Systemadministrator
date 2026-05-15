# Windows-11-Troubleshooting

## Ziel

Diese Anleitung sammelt typische Windows-11-Supportfälle und ein strukturiertes Vorgehen zur Fehleranalyse.

## Grundcheck

Vor tieferer Analyse sollten immer diese Punkte geprüft werden:

1. Seit wann besteht das Problem?
2. Ist nur ein Benutzer oder sind mehrere Benutzer betroffen?
3. Wurde kurz davor etwas geändert, z. B. Update, Treiber, Software oder Hardware?
4. Funktioniert das Problem mit einem anderen Benutzerprofil?
5. Gibt es Fehlermeldungen, Screenshots oder Ereignisprotokolle?

## Bluescreen analysieren

1. Benutzer fragen, ob neue Hardware oder neue Treiber installiert wurden.
2. Gerät neu starten und prüfen, ob der Fehler reproduzierbar ist.
3. Geräte-Manager öffnen:

```text
devmgmt.msc
```

4. Auf Warnsymbole bei Treibern achten.
5. Windows Update-Verlauf prüfen und verdächtige Updates recherchieren.
6. Ereignisanzeige prüfen:

```text
eventvwr.msc
```

7. Falls nötig: abgesicherten Modus oder erweiterte Startoptionen nutzen.

## Langsame Anwendungen

1. Task-Manager öffnen und CPU, RAM, Datenträger und Netzwerk prüfen.
2. Prüfen, ob nur eine Anwendung oder das ganze System langsam ist.
3. Windows-Sicherheitsprüfung starten:

```text
Windows Security > Virus & threat protection > Quick scan
```

4. Datenträgerbereinigung ausführen.
5. Nicht benötigte Programme deinstallieren.
6. Festplattenstatus prüfen:

```cmd
wmic diskdrive get status
```

7. Bei dauerhaft hoher Auslastung Hardware-Upgrade prüfen, z. B. RAM oder SSD.

## Speicherplatzprobleme

1. Datenträgerbereinigung ausführen.
2. Große Benutzerordner identifizieren.
3. Optional ein Analysewerkzeug wie WinDirStat verwenden, nur von offizieller Quelle.
4. Mit dem Benutzer klären, ob Daten nach OneDrive oder auf ein Netzlaufwerk verschoben werden können.
5. Papierkorb, Downloads und temporäre Dateien prüfen.

## Druckerprobleme

1. Druckwarteschlange prüfen und blockierte Jobs löschen.
2. Drucker neu starten.
3. Windows-Druckerproblembehandlung ausführen.
4. Prüfen, ob der richtige Treiber installiert ist.
5. Bei Netzwerkdruckern Printserver prüfen.
6. Testseite drucken.

## Display-Probleme

1. Anzeigeeinstellungen öffnen.
2. Skalierung und Auflösung prüfen.
3. Mehrmonitor-Konfiguration prüfen.
4. Grafikkartentreiber im Geräte-Manager prüfen.

## Sound-Probleme

1. Ausgabegerät prüfen.
2. Lautstärke und Stummschaltung prüfen.
3. Geräte-Manager öffnen und Audiotreiber prüfen.
4. Windows-Problembehandlung für Audio ausführen.

## Informationen zum Gerät erfassen

```text
msinfo32
```

Nützlich für Tickets:

- Gerätename
- Betriebssystemversion
- Modell
- BIOS-Version
- RAM
- Prozessor

## Fehlerquellen dokumentieren

Für Anwendungsfehler sind besonders hilfreich:

- Zuverlässigkeitsüberwachung
- Ereignisanzeige
- Screenshots
- genaue Uhrzeit des Fehlers
- Benutzeraktion direkt vor dem Fehler

Pfad zur Zuverlässigkeitsüberwachung:

```text
Windows-Suche > Zuverlässigkeitsverlauf anzeigen
```
