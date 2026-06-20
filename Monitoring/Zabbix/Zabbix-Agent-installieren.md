# Zabbix Agent 2 installieren

Installation von Zabbix Agent 2 unter Windows und Aufnahme des Windows-Hosts in den Zabbix-Server.

## Zabbix Agent 2 herunterladen

[Zabbix Agent 2 für Windows herunterladen](https://cdn.zabbix.com/zabbix/binaries/stable/7.4/7.4.11/zabbix_agent2-7.4.11-windows-amd64-openssl.msi)

Den Link im Browser öffnen und den Download von Zabbix Agent 2 starten.

## Zabbix Agent 2 installieren

1. Die heruntergeladene MSI-Datei starten.
2. Im Setup die Zabbix-Server-IP auf `<ZABBIX_SERVER_IP>` anpassen.
3. `Add agent location to the PATH` aktivieren.
4. Die Installation abschließen.

## Windows-Host im Zabbix-Server anlegen

1. In der Zabbix-Oberfläche `Datenerfassung > Hosts` öffnen.
2. Oben rechts `Neuer Host` auswählen.
3. Den Namen des Hosts und eine Hostgruppe eingeben.
4. Unter `Schnittstellen` eine Agent-Schnittstelle hinzufügen.
5. IP-Adresse des Windows-Hosts und Port `10050` eintragen.
6. Den neuen Host hinzufügen.
7. Unter `Vorlagen` folgende Vorlage auswählen:

```text
Templates > Windows by Zabbix agent active
```

**Wichtig:** Die richtige Vorlage auswählen, damit die Überwachung funktioniert.
