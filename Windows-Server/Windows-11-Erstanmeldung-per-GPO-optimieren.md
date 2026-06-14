# Lab 4 - Windows-11-Erstanmeldung per GPO optimieren

<img src="images/Lab.png" alt="Lab Screenshot" width="600">

## Ziel

Windows-11-Erstanmeldung ruhiger und reproduzierbarer machen.

## Checkliste

- Neues GPO in der passenden OU erstellen.
- Loopback-Verarbeitung nur aktivieren, wenn sie wirklich gebraucht wird.
- Willkommensseite für Erste Schritte deaktivieren.
- OOBE- und Cloud-Hinweise nach Umgebungsvorgabe reduzieren.
- Consumer-Features und unnötige Hinweise deaktivieren.
- Cortana oder Suchfunktionen nach Vorgabe steuern.
- OneDrive-Verhalten bewusst setzen, nicht zufällig blockieren.
- Microsoft-Edge-Ersteinrichtung und Anmeldeeinstellungen prüfen.
- GPO mit Testbenutzer und Testgerät prüfen.

## Worauf man achten muss

- Loopback-Verarbeitung kann unerwartet Benutzer-GPOs beeinflussen.
- OneDrive- und Edge-Einstellungen können produktive Benutzer stören.
- GPO erst an Test-OU verlinken, nicht direkt breit ausrollen.
- Ergebnis mit `gpresult` prüfen.

## Ergebnis

Die erste Anmeldung ist weniger störend und besser für Rollouts oder Schulungsumgebungen geeignet.
