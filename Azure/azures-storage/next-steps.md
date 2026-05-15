# Next Steps

## 1. Container-Struktur vervollständigen

Lege diese Container an:

- `app-data`
- `configs`
- `archive`

Damit wird klar zwischen Dokumenten, Anwendungsdaten, Konfigurationen und Archivdaten unterschieden.

## 2. Replikation fachlich richtig einordnen

Aktuell ist für das Lernprojekt `LRS` völlig okay. Wenn du jedoch die Aussage treffen willst, dass Daten über mehrere physische Rechenzentren oder Regionen abgesichert sind, musst du die Replikationsart bewusst ändern.

Geeignete Optionen:

- `ZRS`: Schutz über mehrere Verfügbarkeitszonen in einer Region
- `GRS`: Replikation in eine zweite Region
- `RA-GRS`: wie GRS, zusätzlich Lesezugriff auf die Sekundärregion
- `GZRS`: Zonen + zweite Region

## 3. Lifecycle als Projektartefakt dokumentieren

Die Portal-Regel sollte auch als Datei dokumentiert sein. Dafür ist `lifecycle-policy.json` im Projekt abgelegt.

## 4. Azure Function konfigurieren

Ziel:

- bei jeder neuen `backup-status.json` eine Status-Mail senden
- täglich um 08:00 Uhr die 72-Stunden-Warnung prüfen
- Empfänger: Projektbesitzer
- Inhalt:
  - Projektname
  - Status
  - Datum und Uhrzeit
  - verarbeitete Dateien
  - Fehlermeldung
  - Retry-Anzahl

Umsetzung:

1. Blob Trigger für `status/backup-status.json`
2. Timer Trigger für die 72-Stunden-Prüfung
3. SMTP-App-Settings für den E-Mail-Versand

## 4a. Statusdateien ergänzen

Als nächster technischer Schritt schreibt das Backup-Skript nach jedem Lauf eine aktuelle Statusdatei in den Container `status`.

Geplante Dateien:

- `backup-status.json`
- `backup-status-1.json`
- `backup-status-2.json`
- `backup-status-3.json`
- `backup-status-4.json`
- `backup-status-5.json`
- `backup-status-6.json`
- `backup-status-7.json`

Die Datei `backup-status.json` enthält immer den letzten Lauf. Die sieben nummerierten Dateien bilden eine feste Rotation.

## 5. Azure Backup richtig verwenden

Azure Backup sollte in diesem Projekt als Erweiterung sauber eingeordnet werden:

- sinnvoll für `Virtual Machines`
- sinnvoll für `Azure Files`
- sinnvoll für definierte klassische Backup-Richtlinien
- nicht der primäre Ersatz für Blob-Versionierung und Soft Delete

## 6. Portfolio-Formulierung

Eine passende Kurzbeschreibung wäre:

`In diesem Projekt wurde ein automatisiertes Backup eines lokalen Testordners nach Azure Blob Storage aufgebaut. Dabei wurden Blob-Versionierung, Soft Delete, Lifecycle Management, Service-Principal-Authentifizierung und Azure Functions eingesetzt, um Dateien zu sichern, Statusmeldungen auszuwerten und E-Mail-Benachrichtigungen bei Erfolg, Fehler oder ausbleibenden Läufen zu versenden.`
