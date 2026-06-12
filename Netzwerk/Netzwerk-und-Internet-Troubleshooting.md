# Netzwerk- und Internet-Troubleshooting

## Ziel

Kurze Checkliste für Netzwerk- und Internetprobleme.

## Checkliste

- Klären, ob ein Benutzer, mehrere Geräte oder ein ganzer Standort betroffen sind.
- Prüfen, ob interne Systeme erreichbar sind.
- Prüfen, ob externe Dienste erreichbar sind.
- Verbindung prüfen: WLAN, Ethernet, Dockingstation oder Switchport.
- IP-Konfiguration mit `ipconfig /all` prüfen.
- Gateway anpingen.
- Externe IP anpingen, z. B. `8.8.8.8`.
- DNS-Auflösung mit `nslookup` prüfen.
- Mit einem zweiten Gerät im gleichen Netz vergleichen.
- Netzwerkadapter und Treiber im Geräte-Manager prüfen.
- Bei langsamem Internet Speedtest und Task-Manager prüfen.
- Router oder Firewall nur nach Freigabe neu starten.
- Bei mehreren betroffenen Geräten an Netzwerkteam oder Provider eskalieren.

## Nützliche Befehle

```cmd
ipconfig /all
ping <gateway-ip>
ping 8.8.8.8
nslookup google.com
```
