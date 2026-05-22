# Drucker installieren und einrichten

## Ziel

Diese Anleitung beschreibt die Einrichtung eines Netzwerkdruckers über die Druckverwaltung, die Grundkonfiguration am Gerät und die anschließende Verteilung an Clients.

## Ausgangslage

Ein Netzwerkdrucker soll zentral über einen Druckserver bereitgestellt werden. Zusätzlich können Druckoptionen, Papierfächer, Scan-to-Folder und Client-Zuweisung eingerichtet werden.

## Vorbereitung

Vor der Installation prüfen:

- Druckermodell
- IP-Adresse des Druckers
- Standort und Fachkonfiguration
- benötigter Treiber
- bestehende Konfiguration eines alten Druckers
- Freigabename und gewünschter Anzeigename

Wenn ein alter Drucker ersetzt wird, sollten dessen Fach-, Treiber- und Freigabeeinstellungen vorher geprüft werden.

## Treiber vorbereiten

1. Druckermodell ermitteln.
2. Treiber von der Herstellerseite herunterladen.
3. Wenn möglich PCL6-Treiber verwenden.
4. Treiber auf dem Druckserver bereitstellen.

## Drucker auf dem Druckserver hinzufügen

1. Druckverwaltung öffnen.
2. Druckserver auswählen.
3. Vorhandene alte Druckerkonfiguration prüfen.
4. Falls notwendig alte Konfiguration entfernen.
5. Rechtsklick > `Drucker hinzufügen`.
6. TCP/IP-Drucker hinzufügen.
7. IP-Adresse des Druckers eintragen.
8. Treiber auswählen oder neuen Treiber installieren.
9. Druckername und Freigabename sinnvoll setzen.
10. Testseite drucken.

## Druckeinstellungen prüfen

Typische Einstellungen:

- Duplexdruck
- lange Kante
- Papierquelle
- Papierformat
- Fach 1 / Fach 2
- Standarddrucker nach Bedarf

Wenn Fach- oder Druckoptionen nicht sauber übernommen werden, sollte ein anderer Treiber getestet werden.

## Drucker-Webinterface

Über die IP-Adresse des Druckers kann das Webinterface geöffnet werden.

Dort prüfen:

- DNS-Einstellungen
- IPv6 nach Vorgabe aktivieren oder deaktivieren
- Firmwarestand
- Startseite des Druckers
- Papierfächer
- Scan- oder SMB-Ziele

## Scan-to-Folder einrichten

1. Drucker-Webinterface öffnen.
2. Netzwerkordner konfigurieren.
3. Verbindungstyp `SMB` auswählen.
4. UNC-Pfad eintragen, z. B.:

```text
\\SERVER\Scan
```

5. Authentifizierung nach Unternehmensvorgabe setzen.
6. Verbindung testen.
7. Dateiformat, z. B. PDF, festlegen.
8. Scan-Ziel auf der Startseite des Druckers hinterlegen.

## Geräteseite anpassen

Je nach Gerät können häufig verwendete Funktionen auf der Startseite hinterlegt werden, zum Beispiel:

- Kopieren
- Fax
- Status oder Material
- Auftragswarteschlange
- Kurzwahl
- Ausweiskopie
- Scan Center
- Einstellungen

## Drucker auf Clients hinzufügen

1. Systemsteuerung öffnen.
2. Geräte und Drucker öffnen.
3. `Drucker hinzufügen` auswählen.
4. `Der gewünschte Drucker ist nicht aufgelistet` auswählen.
5. Freigegebenen Drucker über Namen hinzufügen:

```text
\\DRUCKSERVER\Freigabename
```

6. Testseite drucken.
7. Bei Bedarf als Standarddrucker festlegen.

## Fehlerbehebung

Wenn Fach- oder Treibereinstellungen nicht korrekt greifen:

- anderen Herstellertreiber testen
- PCL5/PCL6 vergleichen
- alte Druckerwarteschlange entfernen
- Druckserver neu prüfen
- Drucker-Webinterface kontrollieren

## Nachkontrolle

Prüfen:

- Testseite wird gedruckt
- richtiger Treiber ist aktiv
- Duplexdruck funktioniert
- richtiges Fach wird verwendet
- Scan-to-Folder funktioniert
- Drucker kann vom Client hinzugefügt werden

## Dokumentation im Ticket

Festhalten:

- Druckermodell
- IP-Adresse
- Druckserver
- Freigabename
- Treiber
- Testseite erfolgreich: ja/nein
- Scan-Ziel eingerichtet: ja/nein
