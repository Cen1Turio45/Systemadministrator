# Azure Storage Backup - Projektüberblick

## Ziel

Ein lokaler Testordner wird täglich nach Azure Blob Storage gesichert. Zusätzlich werden Statusdateien geschrieben und E-Mail-Benachrichtigungen vorbereitet.

## Architektur

```text
Lokaler Testordner
  |
PowerShell-Skript
  |
Windows Task Scheduler
  |
Azure Blob Storage
  |
Statusdatei im Container status
  |
Azure Function
  |
E-Mail-Benachrichtigung
```

## Azure-Ressourcen

- Storage Account `azurestorage50t`
- Container `documents`
- Prefix `backup-files/`
- Container `status`
- Azure Function App `azure-storage`
- Blob Trigger für `status/backup-status.json`
- Timer Trigger für Warnung nach 72 Stunden ohne Lauf
- Service Principal mit `Storage Blob Data Contributor`

## Wichtige Entscheidungen

- Backup statt Synchronisierung: lokale Löschungen entfernen keine Azure-Dateien.
- Service Principal statt dauerhaftem SAS-Token.
- Statusdatei wird getrennt von den Backup-Dateien gespeichert.
- Azure Function startet keine Backups, sondern wertet nur Statusdateien aus.
- Retry-Logik endet nach maximal drei Versuchen.
- Budgetziel: unter 20 EUR.

## Schutzmechanismen

- Blob-Versionierung gegen Überschreiben.
- Blob Soft Delete gegen versehentliches Löschen.
- Container Soft Delete gegen Container-Löschung.
- Lifecycle Management zur Kostenkontrolle.

## Statusdateien

- `backup-status.json`: letzter bekannter Lauf
- `backup-status-1.json` bis `backup-status-7.json`: rotierende Historie

Wichtige Felder:

```json
{
  "status": "success",
  "processedFileCount": 2,
  "retryCount": 1,
  "lastError": ""
}
```

## Worauf man achten muss

- Ein Lauf gilt nur als erfolgreich, wenn alle Dateien verarbeitet und die Statusdatei geschrieben wurde.
- Fehlgeschlagene Teilläufe dürfen nicht als Erfolg gemeldet werden.
- Secrets dürfen nicht ins GitHub-Repository.
- `AzureWebJobsStorage` und `BackupStorageConnection` dürfen nicht verwechselt werden.
- Replikation bewusst wählen: günstig ist nicht automatisch ausfallsicher.
- Restore muss getestet werden, sonst ist es nur ein Upload und kein brauchbares Backup.

## Bereits getestet

- Upload nach `documents/backup-files/`
- Schreiben von `backup-status.json`
- Rotation der Statusdateien
- Retry-Logik mit absichtlich falschem Zielcontainer
- Wiederherstellung per Blob-Versionierung
- Wiederherstellung per Soft Delete
- Deployment der Azure Function App
- manueller E-Mail-Test über Azure Communication Services

## Noch offen

- automatische Blob-Trigger-Mail nach Statusänderung bestätigen
- automatische Fehlermail nach bewusst fehlerhaftem Backup-Lauf bestätigen
- 72-Stunden-Warnung im normalen Zeitverlauf bestätigen
