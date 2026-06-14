# Lab 2 - Zweiten DNS-Server installieren

<img src="images/Lab.png" alt="Lab Screenshot" width="600">

## Ziel

`PLABDM01` als zusätzlichen DNS-Server einrichten und per DHCP verteilen.

## Checkliste

- Auf `PLABDM01` Rolle `DNS-Server` installieren.
- Auf `PLABDC01` im DNS-Manager Zonentransfers für `Plab.de` aktivieren.
- `PLABDM01` als erlaubten Server für Zonentransfers eintragen.
- Auf `PLABDM01` sekundäre Forward-Lookup-Zone `Plab.de` erstellen.
- `PLABDC01` als Masterserver hinterlegen.
- DHCP-Option `006 DNS Servers` um den zweiten DNS-Server ergänzen.
- DNS-Auflösung auf einem Client testen.
- Test-A-Record anlegen und Replikation prüfen.

## Worauf man achten muss

- Zonentransfer nur für erlaubte DNS-Server aktivieren.
- DHCP verteilt DNS-Server erst nach Lease-Erneuerung oder Client-Neustart.
- Clients müssen weiterhin den Domain-DNS nutzen, nicht externe Resolver.

## Ergebnis

Der zweite DNS-Server kann als zusätzlicher Resolver im Lab verwendet werden.
