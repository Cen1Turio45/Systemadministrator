# Installationsanleitung Zabbix

## Ziel

Zabbix als Monitoring-System installieren und für erste Tests vorbereiten.

## Vorbereitung

- Server oder VM für Zabbix bereitstellen.
- Linux-System aktualisieren.
- Statische IP-Adresse oder festen DNS-Namen vergeben.
- Firewall-Regeln für Weboberfläche und Agent-Kommunikation prüfen.
- Datenbankanforderungen nach Zabbix-Version prüfen.

## Installation

1. Zabbix-Repository für die passende Distribution einbinden.
2. Zabbix-Server, Webfrontend, Agent und Datenbankpakete installieren.
3. Datenbank erstellen.
4. Datenbankschema importieren.
5. Zabbix-Konfiguration mit Datenbankname, Benutzer und Passwort anpassen.
6. Zabbix-Server und Webserver starten.
7. Dienste für Autostart aktivieren.
8. Webinstaller öffnen und Einrichtung abschließen.

## Nachkontrolle

- Weboberfläche ist erreichbar.
- Login funktioniert.
- Zabbix-Server-Dienst läuft.
- Zabbix-Agent ist erreichbar.
- Erster Host wird erkannt oder manuell angelegt.
- Testweise ein einfacher Trigger oder Item geprüft.

## Worauf man achten muss

- Datenbankpasswort nicht öffentlich dokumentieren.
- Firewall zwischen Server und Agents prüfen.
- Zeit und Zeitzone sauber setzen.
- Templates nicht blind übernehmen, sondern passend zum System auswählen.
