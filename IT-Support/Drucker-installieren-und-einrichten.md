# Drucker installieren und einrichten

## Ziel

Anleitung zur Einrichtung von Druckern bei Geschäfts- und Privatkunden.

## Vorab klären

- Handelt es sich um einen Geschäfts- oder Privatkunden?
- Druckermodell und Hersteller prüfen.
- Anschlussart klären: USB, LAN, WLAN oder Druckserver.
- IP-Adresse, Standort und gewünschter Druckername klären.
- Soll auch Scannen eingerichtet werden?
- Gibt es einen alten Drucker, dessen Einstellungen übernommen werden müssen?

## Geschäftskunden

### 1. Druckserver

1. Druckermodell und passenden Treiber von der Herstellerseite herunterladen.
2. Wenn möglich PCL6-Treiber verwenden.
3. Auf dem Druckserver die Druckverwaltung öffnen.
4. Vorhandene alte Druckerkonfiguration prüfen.
5. Neuen TCP/IP-Drucker hinzufügen.
6. IP-Adresse des Druckers eintragen.
7. Treiber auswählen oder installieren.
8. Druckername und Freigabename sinnvoll setzen.
9. Testseite am Druckserver drucken.

### 2. Druckereinstellungen

1. Duplexdruck prüfen.
2. Papierformat prüfen.
3. Papierfächer prüfen.
4. Standardwerte wie Farbe/Schwarzweiß setzen.
5. Berechtigungen und Freigabe prüfen.
6. Bei Fach- oder Treiberproblemen alternativen Herstellertreiber testen.

### 3. Direkte Einstellungen am Drucker

1. Webinterface über die Drucker-IP öffnen.
2. Gerätename und Standort prüfen.
3. DNS, Gateway und Netzwerkeinstellungen prüfen.
4. Firmwarestand prüfen.
5. Papierfächer und Standardfunktionen prüfen.
6. Falls benötigt Scan-to-Folder einrichten.
7. SMB-Pfad, Benutzer und Berechtigungen testen.

### 4. Drucker mit Computer verbinden

1. Am Client `\\DRUCKSERVER\Freigabename` öffnen.
2. Drucker hinzufügen.
3. Testseite vom Client drucken.
4. Bei Bedarf als Standarddrucker setzen.
5. Drucken aus einer echten Anwendung testen.

## Privatkunden

1. Druckermodell prüfen.
2. Treiber und Software von der Herstellerseite herunterladen.
3. Drucker per USB, LAN oder WLAN verbinden.
4. Drucker in Windows hinzufügen.
5. Testseite drucken.
6. Wenn der Scanner nicht sauber funktioniert, NAPS2 installieren.
7. Scanner in NAPS2 einrichten und Testscan durchführen.

## Worauf man achten muss

- Keine Treiber von unbekannten Downloadseiten verwenden.
- Bei Geschäftskunden möglichst über Druckserver arbeiten.
- Scan-to-Folder hängt oft an SMB, Benutzerrechten oder falschem Pfad.
- Drucker-IP sollte fest vergeben oder per DHCP-Reservierung gesichert sein.
- Bei mehreren gleichen Modellen eindeutige Namen und Standorte verwenden.
