# Azure Storage Project

Dieses Projekt baut eine kleine, praxisnahe Backup- und Restore-Basis in Azure auf.

Die ausführliche Projektplanung liegt in [PROJECT_PLAN.md](PROJECT_PLAN.md).

## Projektziel

Ein lokaler Testordner wird täglich automatisiert nach Azure Blob Storage gesichert. Die Dateien werden gegen Löschen und Überschreiben geschützt. Zusätzlich wird eine Azure Function für E-Mail-Benachrichtigungen bei Erfolg, Fehler und ausbleibenden Läufen vorbereitet.

## Aktueller Stand

Bereits umgesetzt und getestet:

- `Storage Account` erstellt
- Container `documents` erstellt
- Container `status` erstellt
- Backup-Dateien werden unter `documents/backup-files/` abgelegt
- `Versionsverwaltung für Blobs` aktiviert
- `Vorläufiges Löschen für Blobs` aktiviert
- `Vorläufiges Löschen für Container` aktiviert
- Überschreiben einer Datei getestet
- Wiederherstellung einer alten Version getestet
- Löschen einer Datei getestet
- Wiederherstellung per Soft Delete getestet
- erste Lifecycle-Regel im Portal angelegt
- Azure Function App `azure-storage` deployed
- HTTP-Testmail erfolgreich über Azure Communication Services versendet
- Statusdateien werden in den Container `status` geschrieben
- 7er-Rotation der Statusdateien wurde getestet
- Fehlerfall mit maximal drei Versuchen wurde getestet

## Wichtige fachliche Einordnung

- `LRS` ist gut für den günstigen Einstieg, repliziert aber nicht über mehrere Rechenzentren.
- Wenn Daten auch bei einem Ausfall eines gesamten Rechenzentrums oder einer Region verfügbar bleiben sollen, brauchst du je nach Ziel mindestens `GRS`, `RA-GRS`, `GZRS` oder `RA-GZRS`.
- `Versioning` schützt vor Überschreiben.
- `Soft Delete` schützt vor versehentlichem Löschen.
- `Lifecycle Management` hilft bei der Kostenoptimierung.
- `Azure Backup` ist eher für klassische Backup-Szenarien wie VMs, Azure Files oder definierte Restore-Policies relevant, nicht als Ersatz für Blob-Versionierung.

## Projektdateien

- [main.bicep](main.bicep)
- [lifecycle-policy.json](lifecycle-policy.json)
- [next-steps.md](next-steps.md)
- [backup-to-azure.ps1](backup-to-azure.ps1)
- [backup-settings.json](backup-settings.json)
- [register-backup-task.ps1](register-backup-task.ps1)
- [AUTOMATION.md](AUTOMATION.md)
- [function-app](function-app)

## Nächster sinnvoller Ausbau

- weitere Container `app-data`, `configs`, `archive` anlegen
- Replikationsart bewusst prüfen und ggf. auf `GRS` oder `GZRS` umstellen
- Lifecycle-Regel als Datei dokumentieren
- lokalen täglichen Upload bestimmter Dateien nach Azure automatisieren
- Azure-Authentifizierung ohne SAS über Service Principal einrichten
- Statusdateien im Container `status` erzeugen
- Azure Function für E-Mail-Benachrichtigungen konfigurieren
- Azure Backup als Erweiterung für geeignete Workloads einordnen
