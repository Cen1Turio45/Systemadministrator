# Lab 4 - Windows-11-Erstanmeldung per GPO optimieren

<img src="images/Lab.png" alt="Lab Screenshot" width="600">

## Ziel

Eine Gruppenrichtlinie soll die Windows-11-Erstanmeldung vereinfachen und störende Assistenten oder Hinweise reduzieren.

## GPO erstellen

1. Auf dem Domain Controller die `Group Policy Management Console` öffnen.
2. Unter der Domäne ein neues GPO erstellen.
3. GPO sinnvoll benennen, z. B. `Windows 11 - Optimierte Erstanmeldung`.
4. GPO bearbeiten.

## Einstellungen

### Loopback-Verarbeitung

Pfad: `Computer Configuration > Policies > Administrative Templates > System > Group Policy`

- `Configure user Group Policy loopback processing mode` aktivieren
- Modus: `Merge`

### Anmeldung

Pfad: `Computer Configuration > Administrative Templates > System > Logon`

- `Willkommensseite für Erste Schritte bei der Anmeldung nicht anzeigen` aktivieren

### OOBE und Cloud-Inhalte

Pfad: `Computer Configuration > Administrative Templates > Windows Components > OOBE`

- OOBE-bezogene Hinweise deaktivieren, soweit in der Umgebung sinnvoll

Pfad: `Computer Configuration > Administrative Templates > Windows Components > Cloud Content`

- Unnötige Consumer- und Cloud-Hinweise deaktivieren

### Suche und OneDrive

Pfad: `Computer Configuration > Administrative Templates > Windows Components > Search`

- `Cortana zulassen` deaktivieren

Pfad: `Computer Configuration > Administrative Templates > Windows Components > OneDrive`

- OneDrive-Synchronisierung nach Bedarf steuern

### Microsoft Edge

Pfad: `Computer Configuration > Administrative Templates > Microsoft Edge`

- Ersteinrichtungsdialoge reduzieren
- Browser-Anmeldeeinstellungen nach Vorgabe der Umgebung setzen

## Ergebnis

Die Windows-11-Erstanmeldung wird ruhiger und reproduzierbarer. Das ist besonders hilfreich bei Rollouts, Schulungsumgebungen und standardisierten Client-Setups.
