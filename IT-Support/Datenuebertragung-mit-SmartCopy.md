# Datenübertragung mit SmartCopy

## Ziel

Kurze Checkliste für die Datenübertragung von einem alten auf ein neues Gerät.

## Checkliste

- Immer eine Backup-Platte bereithalten. Wenn möglich zuerst SATA auf SATA klonen, bevor von SATA auf NVMe gewechselt wird.
- Bei SATA auf NVMe prüfen, ob Windows die benötigten NVMe-Treiber hat. Ohne passenden NVMe-Treiber kann die neue Platte nach dem Klonen nicht booten.
- Prüfen, ob ein Microsoft-Konto aktiv genutzt wird. Zur Sicherheit vor dem Klonen einen lokalen Admin erstellen und ein Passwort setzen, damit man den Microsoft-Konto-Login notfalls umgehen kann.
- Prüfen, ob BitLocker aktiv ist. BitLocker vor der Datenübertragung deaktivieren, sonst kann es auf der neuen Platte zu Boot-Problemen kommen.
- Hard Resets vermeiden, wenn die Festplatte in einen anderen Rechner eingebaut wurde. Das kann die Boot-Partition beschädigen und unnötige Probleme verursachen.
- Quelle und Ziel vor dem Start eindeutig prüfen, damit nicht versehentlich die falsche Platte überschrieben wird.

## Ticket-Dokumentation

- Quellgerät und Zielgerät
- verwendete Datenträger
- Backup-Platte vorhanden: ja/nein
- BitLocker deaktiviert: ja/nein
- lokaler Admin vorhanden: ja/nein
- Starttest nach der Übertragung erfolgreich: ja/nein
