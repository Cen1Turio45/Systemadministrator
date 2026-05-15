# Netzwerk- und Internet-Troubleshooting

## Ziel

Diese Anleitung beschreibt ein strukturiertes Vorgehen bei Netzwerk- und Internetproblemen im Support.

## Grundprinzip

Zuerst den Umfang klären:

- Ist ein Benutzer betroffen?
- Sind mehrere Geräte betroffen?
- Ist ein ganzer Standort betroffen?
- Funktionieren interne Systeme?
- Funktionieren externe Dienste?

## Einzelner Client ohne Internet

1. Verbindung prüfen: WLAN oder Ethernet?
2. IP-Konfiguration anzeigen:

```cmd
ipconfig /all
```

3. Gateway pingen:

```cmd
ping <gateway-ip>
```

4. Externe IP pingen:

```cmd
ping 8.8.8.8
```

5. DNS prüfen:

```cmd
nslookup google.com
```

6. Mit einem zweiten Gerät im gleichen Netz vergleichen.
7. Netzwerkadapter im Geräte-Manager prüfen.
8. Treiber aktualisieren oder Gerät neu starten.

## Langsames Internet

1. Speedtest am betroffenen Gerät durchführen.
2. Speedtest an einem zweiten Gerät im gleichen Netz durchführen.
3. Prüfen, ob WLAN oder Ethernet genutzt wird.
4. Task-Manager öffnen und Netzwerkauslastung prüfen.
5. Netzwerkadapter prüfen:

```text
Geräte-Manager > Netzwerkadapter > Eigenschaften > Erweitert
```

6. Speed & Duplex prüfen, z. B. `1.0 Gbps Full Duplex`, falls passend.
7. Bei mehreren betroffenen Geräten an Netzwerkteam oder Provider eskalieren.

## Ganzer Standort ohne Internet

1. Prüfen, ob alle Benutzer betroffen sind.
2. Interne Systeme testen, z. B. Fileserver oder Drucker.
3. Externe Webseiten testen.
4. M365 oder andere Cloud-Dienste prüfen.
5. Router, Firewall und Providerstatus prüfen.
6. Router oder Firewall nur mit Freigabe neu starten.
7. Bei Verdacht auf Providerstörung Ticket beim ISP eröffnen.

## Eskalationsinformationen

Für Netzwerkteam oder Provider erfassen:

- Standort
- Startzeitpunkt
- betroffene Benutzeranzahl
- interne Systeme erreichbar ja/nein
- externe Webseiten erreichbar ja/nein
- Gateway erreichbar ja/nein
- DNS-Auflösung erfolgreich ja/nein
- durchgeführte Tests

## Abschluss

Nach der Lösung erneut testen und im Ticket dokumentieren:

- Ursache
- Lösung
- betroffene Systeme
- Dauer der Störung
- mögliche Verbesserung für die Zukunft
