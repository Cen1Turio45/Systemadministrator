# Foundation - Netzwerkaufbau mit pfSense und Hyper-V

## Ziel

Aufbau einer virtuellen Netzwerkumgebung mit pfSense als zentraler Firewall. Die Umgebung dient als Grundlage für weitere Windows-Server-, Netzwerk- und Security-Labs.

## Netzwerkstruktur

| Netz | Hyper-V-Switch | IP-Bereich | Zweck |
| --- | --- | --- | --- |
| WAN | External Switch | `10.71.31.0/24` | Verbindung zum externen Netz |
| LAN | Internal Switch | `192.168.0.0/24` | internes Servernetz |
| DMZ | Private Switch | `192.168.1.0/24` | abgeschottete Testzone |

## pfSense-VM

### Vorbereitung

1. pfSense-ISO herunterladen.
2. ISO bei Bedarf mit 7-Zip entpacken.
3. In Hyper-V eine neue VM erstellen.
4. Secure Boot deaktivieren.
5. Mindestens 4 GB RAM und 4 virtuelle Prozessoren zuweisen.
6. Drei Netzwerkadapter hinzufügen: WAN, LAN und DMZ.

### Grundkonfiguration

```text
WAN: 10.71.31.210/24
Benutzer: admin
Passwort: 1!demo
```

Das Webinterface wird aktiviert, damit die Firewall später über den Browser verwaltet werden kann.

## Testserver

| Server | Netz | Zweck |
| --- | --- | --- |
| DC01 | WAN / Verwaltung | zukünftiger Domain Controller und Administrationsserver |
| LAN-Server | LAN | interne Tests |
| DMZ-Server | DMZ | Simulation eines abgeschotteten Dienstes |

## DC01 vorbereiten

1. Windows Server 2025 installieren.
2. Virtuelle Festplatte mit 150 GB verwenden.
3. Computername auf `DC01` setzen.
4. Remotedesktop aktivieren.
5. Zeitzone und statische IP-Adresse konfigurieren.
6. Windows Updates installieren.
7. Checkpoint in Hyper-V erstellen.

## Zusätzliche Festplatte

1. Über die Hyper-V-Einstellungen eine zweite virtuelle Festplatte hinzufügen.
2. Festplatte im Datenträger-Manager initialisieren.
3. Volume erstellen und formatieren.

Wichtig: Nicht versehentlich den Speicherort einer bestehenden Disk ändern. Das kann die virtuelle Maschine beschädigen.

## Installationsdateien

1. Auf dem Host einen USB-Stick mit dem Ordner `htsupport` einbinden.
2. Ordner als Netzwerkfreigabe bereitstellen.
3. Dateien in der VM nach `C:\htsupport` kopieren.
4. Von dort aus die weitere Softwareinstallation durchführen.

## Domain Controller und NetMan

Nach der Grundkonfiguration wird ein weiterer Checkpoint erstellt. Danach beginnt die Einrichtung des Domain Controllers. Einzelne Installationsschritte zu NetMan werden aus rechtlichen Gründen nicht detailliert dokumentiert.

## Best Practices

- Nach größeren Arbeitsschritten Checkpoints erstellen.
- Vor Änderungen an Datenträgern Sicherungen oder Checkpoints anlegen.
- Secure Boot bei pfSense deaktiviert lassen.
- Firewall-Regeln schrittweise erstellen und testen.
- Verbindungen mit Ping, DNS-Abfragen und Firewall-Logs prüfen.
- Export und Import virtueller Maschinen nur in Testumgebungen verwenden.

## Ergebnis

Die Foundation-Umgebung stellt eine wiederverwendbare Grundlage für weitere Labs bereit. WAN, LAN und DMZ sind logisch getrennt und können über pfSense kontrolliert miteinander kommunizieren.
