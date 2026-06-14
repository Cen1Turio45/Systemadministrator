# Azure Function App - Backup Notifications

## Ziel

Statusdateien aus dem Backup-Projekt auswerten und E-Mail-Benachrichtigungen verschicken.

## Functions

- `backup_status_blob_trigger`: reagiert auf `status/backup-status.json`.
- `backup_warning_timer_trigger`: prüft täglich, ob seit 72 Stunden kein Backup lief.
- `send_test_email`: manueller E-Mail-Test.
- `check_warning`: manueller Test der Warnlogik.

## App Settings

- `AzureWebJobsStorage`
- `BackupStorageConnection`
- `PROJECT_NAME`
- `STATUS_CONTAINER_NAME`
- `CURRENT_STATUS_BLOB_NAME`
- `WARNING_THRESHOLD_HOURS`
- `COMMUNICATION_SERVICES_CONNECTION_STRING`
- `ACS_EMAIL_SENDER`
- `MAIL_TO`
- `WEBSITE_TIME_ZONE`

## Worauf man achten muss

- `AzureWebJobsStorage` ist für die Function Runtime.
- `BackupStorageConnection` zeigt auf den Storage Account mit dem Container `status`.
- Connection Strings und ACS-Zugangsdaten sind Secrets.
- `WEBSITE_TIME_ZONE=W. Europe Standard Time` setzen, wenn der Timer nach deutscher Zeit laufen soll.
- Blob Trigger nur auf die aktuelle Statusdatei legen, nicht auf die rotierende Historie.

## Befehle

Lokal starten:

```powershell
func start
```

Deployment:

```powershell
.\deploy-function-app.ps1
```

App Settings setzen:

```powershell
.\configure-function-app-settings.ps1 `
  -ResourceGroupName "<RESOURCE_GROUP>" `
  -BackupStorageConnection "<STORAGE_CONNECTION_STRING>" `
  -CommunicationServicesConnectionString "<ACS_CONNECTION_STRING>" `
  -AcsEmailSender "<ABSENDER_ADRESSE>" `
  -MailTo "<EMAIL>"
```
