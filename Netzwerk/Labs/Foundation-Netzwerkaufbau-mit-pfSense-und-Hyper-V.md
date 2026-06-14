# Foundation - Netzwerkaufbau mit pfSense und Hyper-V

## Ziel

Wiederverwendbare Grundlage für weitere Windows-Server-, Netzwerk- und Security-Labs.

## Netzwerkstruktur

| Netz | Hyper-V-Switch | IP-Bereich | Zweck |
| --- | --- | --- | --- |
| WAN | External Switch | `10.71.31.0/24` | externes Netz |
| LAN | Internal Switch | `192.168.0.0/24` | internes Servernetz |
| DMZ | Private Switch | `192.168.1.0/24` | abgeschottete Testzone |

## Checkliste

- pfSense-VM mit WAN, LAN und DMZ-Adapter erstellen.
- Secure Boot für pfSense deaktivieren.
- WAN, LAN und DMZ eindeutig den Hyper-V-Switches zuordnen.
- pfSense-Webinterface aktivieren.
- DC01 mit statischer IP, Remotedesktop und Updates vorbereiten.
- Nach Grundkonfiguration Checkpoint erstellen.
- Zusätzliche Datenträger nur nach Sicherung oder Checkpoint ändern.
- Firewall-Regeln schrittweise erstellen und testen.
- Verbindungen mit Ping, DNS-Abfragen und Firewall-Logs prüfen.

## Worauf man achten muss

- Adapterverwechslungen sind die häufigste Fehlerquelle.
- DMZ darf nicht versehentlich wie ein internes LAN behandelt werden.
- Checkpoints vor größeren Umbauten sparen Zeit.
- Datenträgerpfade in Hyper-V nicht unüberlegt ändern.
- NetMan-Details werden aus rechtlichen Gründen nicht dokumentiert.

## Ergebnis

WAN, LAN und DMZ sind getrennt und können über pfSense kontrolliert miteinander kommunizieren.
