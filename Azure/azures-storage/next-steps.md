# Next Steps

## Offen

- Containerstruktur fachlich erweitern: `app-data`, `configs`, `archive`.
- Replikationsart bewusst wählen: `LRS`, `ZRS`, `GRS`, `RA-GRS` oder `GZRS`.
- Lifecycle-Regel als Datei aktuell halten.
- automatische Status-Mail nach `backup-status.json` bestätigen.
- 72-Stunden-Warnung im echten Zeitverlauf testen.
- Azure Backup sauber als Ergänzung einordnen, nicht als Ersatz für Blob-Versionierung.

## Worauf man achten muss

- `LRS` ist günstig, aber keine Absicherung gegen Regionsausfall.
- Statusdateien und Backup-Dateien sollten getrennt bleiben.
- Azure Function darf nur auswerten und benachrichtigen, nicht lokale Backups starten.
- Secrets gehören in App Settings oder lokale Umgebungsvariablen.
- Ein Restore-Test ist wichtiger als nur ein erfolgreicher Upload.
