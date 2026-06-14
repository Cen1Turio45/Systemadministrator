# Netzwerk

Kurze Checklisten und Labs zu Netzwerkdiagnose, LANCOM und pfSense.

## Checklisten

| Thema | Fokus |
| --- | --- |
| [Netzwerk- und Internet-Troubleshooting](Netzwerk-und-Internet-Troubleshooting.md) | Client, Standort, Gateway, DNS und Provider eingrenzen |
| [LANCOM VPN-Verbindung erstellen](LANCOM-VPN-Verbindung-erstellen.md) | Profil, Gateway, Authentifizierung, Zielnetz und Verbindungstest |
| [LANCOM VPN-Verbindung ändern](LANCOM-VPN-Verbindung-aendern.md) | altes Profil sichern, neue Daten setzen und interne Dienste testen |
| [Wichtige Begriffe](Wichtige-Begriffe.md) | VPN-, Routing- und Netzwerkbegriffe kurz erklärt |

## Labs

| Lab | Fokus |
| --- | --- |
| [Foundation: Netzwerkaufbau mit pfSense und Hyper-V](Labs/Foundation-Netzwerkaufbau-mit-pfSense-und-Hyper-V.md) | WAN, LAN, DMZ und Hyper-V-Switches |
| [Windows-Testumgebung mit pfSense-Firewall](Labs/Windows-Testumgebung-mit-pfSense-Firewall.md) | pfSense, AD DS, DNS, DHCP und Windows-Client |
| [Zweiten DNS-Server installieren](Labs/Zweiten-DNS-Server-installieren.md) | sekundärer DNS, Zonentransfer und DHCP-Option |
| [Zusätzliches HR-Netzwerk hinzufügen](Labs/Zusaetzliches-HR-Netzwerk-hinzufuegen.md) | neues Netz, NAT, Firewall-Regeln und Erreichbarkeit |

## Worauf man achten muss

- DNS-Fehler wirken oft wie Internet- oder Anwendungsfehler.
- Gateway, DNS und Firewall-Regeln immer getrennt prüfen.
- Neue Netze brauchen Routing, NAT und Firewall-Regeln.
