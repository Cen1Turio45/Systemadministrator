# Automatisierter Upload nach Azure Blob Storage

## Ziel

PowerShell-Skript und Task Scheduler laden lokale Dateien automatisch nach Azure Blob Storage hoch.

## Zielstruktur

- Storage Account: `azurestorage50t`
- Backup-Container: `documents`
- Backup-Prefix: `backup-files/`
- Status-Container: `status`

## Dateien

- [backup-settings.json](backup-settings.json)
- [backup-to-azure.ps1](backup-to-azure.ps1)
- [register-backup-task.ps1](register-backup-task.ps1)
- [function-app](function-app)

## Authentifizierung

| Modus | Einsatz |
| --- | --- |
| `servicePrincipal` | beste Wahl für automatische Läufe |
| `azcli` | gut für manuelle Tests mit angemeldetem Konto |
| `sas` | schneller Test, aber nicht als Dauerlösung |

Für `servicePrincipal` werden benötigt:

- `AZURE_TENANT_ID`
- `AZURE_CLIENT_ID`
- `AZURE_CLIENT_SECRET`
- Rolle `Storage Blob Data Contributor` auf dem Storage Account

## Test

```powershell
.\backup-to-azure.ps1
```

Task Scheduler registrieren:

```powershell
.\register-backup-task.ps1
```

Andere Uhrzeit:

```powershell
.\register-backup-task.ps1 -RunTime "07:30"
```

## Worauf man achten muss

- Secrets nicht in `backup-settings.json` speichern.
- Statusdateien getrennt von Backup-Dateien ablegen.
- Logs lokal halten und nicht ins Repository committen.
- Uploadfehler müssen einen `failed`-Status schreiben.
- Task Scheduler muss verpasste Läufe nachholen können.
- Function App wertet Status aus, startet aber keine lokalen Backups.
