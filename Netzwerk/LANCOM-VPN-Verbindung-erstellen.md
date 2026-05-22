# LANCOM VPN-Verbindung erstellen

## Ziel

Diese Anleitung beschreibt die grundsätzliche Erstellung einer VPN-Verbindung mit LANCOM-Komponenten.

## Ausgangslage

Ein Benutzer benötigt eine VPN-Verbindung zum Firmennetz. Dafür müssen sowohl das VPN-Profil auf der LANCOM-Seite als auch die Verbindung im VPN-Client sauber angelegt werden.

## Vorbereitung

Vor der Einrichtung prüfen:

- gewünschter Benutzer
- Zielnetz
- Gateway-Adresse oder DNS-Name
- VPN-Protokoll, z. B. IPsec/IKEv2
- Authentifizierungsart
- benötigte lokale Netzwerke
- virtueller IP-Pool

Zugangsdaten und Pre-Shared Keys werden nicht öffentlich dokumentiert und müssen aus der internen Dokumentation übernommen werden.

## VPN-Profil erstellen

1. LANCOM-Verwaltung öffnen.
2. Bereich für VPN-Verbindungen öffnen.
3. Neues IPsec-Profil erstellen.
4. Namen des Profils setzen.
5. Sicherheitsprofil auswählen.
6. Lokale Netzwerke eintragen.
7. Virtuellen IP-Pool auswählen.
8. Authentifizierung nach Vorgabe konfigurieren.
9. Lokalen und entfernten Identifier setzen.
10. Profil speichern.

## VPN-Client einrichten

1. VPN-Client öffnen.
2. Neue Verbindung erstellen.
3. Verbindungstyp auswählen, z. B. IPsec/IKEv2.
4. Gateway eintragen.
5. Benutzer-ID und Authentifizierungsdaten eintragen.
6. Verbindung speichern.
7. Verbindung testen.

## Nachkontrolle

Prüfen:

- VPN-Verbindung wird aufgebaut
- Benutzer erhält eine passende virtuelle IP-Adresse
- internes Zielnetz ist erreichbar
- DNS-Auflösung funktioniert, falls benötigt
- Zugriff auf benötigte Dienste ist möglich

## Sicherheitshinweis

Pre-Shared Keys, Passwörter, echte Gateway-Adressen und Benutzerdaten gehören nicht in öffentliche Dokumentationen. In GitHub werden nur Platzhalter oder neutrale Beispiele verwendet.

## Dokumentation im Ticket

Festhalten:

- Benutzer
- Zielnetz
- Profilname
- Client eingerichtet
- Verbindung getestet
- Dokumentation aktualisiert
