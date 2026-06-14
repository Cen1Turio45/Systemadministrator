# Azure Storage Backup

## Ziel

Lokale Testdateien automatisiert nach Azure Blob Storage sichern und gegen versehentliches Löschen oder Überschreiben schützen.

## Umgesetzt

- Storage Account und Container `documents` erstellt.
- Backup-Dateien unter `documents/backup-files/` abgelegt.
- Container `status` für Statusdateien erstellt.
- Blob-Versionierung aktiviert.
- Soft Delete für Blobs und Container aktiviert.
- Lifecycle-Regel vorbereitet.
- PowerShell-Uploadskript erstellt.
- Task Scheduler für tägliche Läufe vorbereitet.
- Azure Function App für Status- und E-Mail-Benachrichtigungen deployed.
- Retry-Logik und Statusrotation getestet.

## Worauf man achten muss

- Backup ist keine Synchronisierung: lokale Löschungen sollen Azure-Dateien nicht automatisch entfernen.
- `Versioning` schützt vor Überschreiben.
- `Soft Delete` schützt vor versehentlichem Löschen.
- `Lifecycle Management` verhindert unnötig hohe Langzeitkosten.
- `LRS` ist günstig, schützt aber nicht vor Ausfall einer ganzen Region.
- Service Principal ist für automatische Läufe sauberer als ein dauerhaftes SAS-Token.
- Secrets gehören nicht ins Repository, sondern in Benutzerumgebungsvariablen oder Azure App Settings.

## Projektdateien

- [backup-to-azure.ps1](backup-to-azure.ps1)
- [register-backup-task.ps1](register-backup-task.ps1)
- [backup-settings.json](backup-settings.json)
- [AUTOMATION.md](AUTOMATION.md)
- [PROJECT_PLAN.md](PROJECT_PLAN.md)
- [function-app](function-app)

## Noch sinnvoll zu prüfen

- automatische Erfolgsmail nach normalem Backup-Lauf
- automatische Fehlermail nach bewusst fehlerhaftem Lauf
- Warnmail nach 72 Stunden ohne Backup-Lauf
- Replikationsart bewusst auswählen: `LRS`, `GRS`, `GZRS` oder `RA-GZRS`
