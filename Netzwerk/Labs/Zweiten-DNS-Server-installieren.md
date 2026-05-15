# Lab 2 - Zweiten DNS-Server installieren

<img src="images/Lab.png" alt="Lab Screenshot" width="600">

## Ziel

PLABDM01 soll als zusätzlicher DNS-Server eingerichtet werden. Anschließend wird ein Testeintrag erstellt und die DNS-Konfiguration per DHCP verteilt.

## Schritte

1. Auf `PLABDM01` die Rolle `DNS-Server` installieren.
2. Auf `PLABDC01` den DNS-Manager öffnen.
3. In der Zone `Plab.de` die Zonentransfers aktivieren.
4. `PLABDM01` als erlaubten Server für Zonentransfers eintragen.
5. Auf `PLABDM01` eine neue sekundäre Forward-Lookup-Zone erstellen.
6. Als Zonenname `Plab.de` eintragen.
7. Als Masterserver die IP-Adresse von `PLABDC01` hinterlegen.
8. Im DHCP-Manager die Option `006 DNS Servers` anpassen und den zusätzlichen DNS-Server eintragen.

## Test

- DNS-Auflösung auf einem Client prüfen.
- Testweise einen A-Record, z. B. `webserver.plab.de`, anlegen.
- Prüfen, ob der Eintrag auf dem zweiten DNS-Server sichtbar ist.

## Ergebnis

Der zweite DNS-Server ist eingerichtet und kann als zusätzlicher Resolver im Netzwerk verwendet werden.
