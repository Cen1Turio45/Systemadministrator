# Auto-Enrollment Policy erstellen

## Ziel

Kurze Checkliste zum Aktivieren von Auto-Enrollment für Zertifikate.

## Checkliste

- Prüfen, ob die CA Zertifikate ausstellt.
- In der CA unter `Issued Certificates` aktuellen Stand prüfen.
- Auf dem Domain Controller `Group Policy Management` öffnen.
- Neues GPO für Auto-Enrollment erstellen.
- Pfad öffnen: `Computer Configuration > Policies > Windows Settings > Public Key Policies > Certificate Services Client > Auto-Enrollment`.
- Auto-Enrollment auf `Enabled` setzen.
- Erneuerung abgelaufener Zertifikate aktivieren.
- Aktualisierung von Zertifikaten über Templates aktivieren.
- GPO mit der passenden OU oder Domain verknüpfen.
- Auf dem CA-Server die Zertifikatvorlage öffnen.
- Gruppe, z. B. `Domain Computers`, mit `Read`, `Enroll` und `Autoenroll` berechtigen.
- Nach Replikation in `Issued Certificates` prüfen, ob neue Zertifikate ausgestellt wurden.
