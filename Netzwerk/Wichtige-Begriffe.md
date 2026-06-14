# Wichtige Begriffe

## Ziel

Kurze Erklärung wichtiger Netzwerk- und VPN-Begriffe.

## VPN

| Begriff | Bedeutung |
| --- | --- |
| IPsec | Protokollfamilie für verschlüsselte VPN-Verbindungen |
| IKE | Schlüsselaushandlung für IPsec-Verbindungen |
| IKEv1 | ältere Variante, oft noch bei Legacy-Geräten oder alten VPN-Profilen |
| IKEv2 | modernere Variante, stabiler bei Verbindungswechseln und meist bevorzugt |
| Pre-Shared Key | gemeinsames Geheimnis für die VPN-Authentifizierung |
| Phase 1 | Aufbau des sicheren Kanals zwischen den VPN-Gateways |
| Phase 2 | Aushandlung der eigentlichen Netz-zu-Netz- oder Client-zu-Netz-Verbindung |

## Wann IKEv1 verwendet wird

- wenn ein älteres Gateway nur IKEv1 unterstützt
- wenn bestehende Legacy-VPNs nicht kurzfristig umgestellt werden können
- wenn Hersteller- oder Kundenvorgaben IKEv1 verlangen

Wenn möglich sollte IKEv2 bevorzugt werden.

## Netzwerk

| Begriff | Bedeutung |
| --- | --- |
| Gateway | Ziel, über das ein Gerät andere Netze erreicht |
| DNS | löst Namen wie `server.firma.local` in IP-Adressen auf |
| DHCP | verteilt IP-Adressen und Optionen automatisch |
| NAT | übersetzt interne IP-Adressen nach außen |
| VLAN | logische Trennung eines Netzwerks auf Switch-Ebene |
| Firewall-Regel | erlaubt oder blockiert Datenverkehr zwischen Quellen und Zielen |
