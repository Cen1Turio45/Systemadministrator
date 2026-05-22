# LANCOM VPN-Verbindung erstellen

## Ziel

Diese Anleitung beschreibt die grundsätzliche Erstellung einer VPN-Verbindung mit LANCOM-Komponenten.

## Vorbereitung

Vor der Einrichtung prüfen:

- gewünschter Benutzer
- Zielnetz
- Gateway-Adresse oder DNS-Name
- VPN-Protokoll, z. B. IPsec/IKEv2
- Authentifizierungsart
- benötigte lokale Netzwerke
- virtueller IP-Pool

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

## Client-Verbindung anlegen

1. VPN-Client öffnen.
2. Neue Verbindung erstellen.
3. Verbindungstyp auswählen, z. B. IPsec/IKEv2.
4. Gateway eintragen.
5. Benutzer-ID und Authentifizierungsdaten eintragen.
6. Verbindung speichern.
7. Verbindung testen.

## Sicherheitshinweis

Pre-Shared Keys, Passwörter, echte Gateway-Adressen und Benutzerdaten gehören nicht in öffentliche Dokumentationen. In GitHub werden nur Platzhalter oder neutrale Beispiele verwendet.

## Dokumentation im Ticket

Festhalten:

- Benutzer
- Zielnetz
- Profilname
- Client eingerichtet
- Verbindung getestet
- Doku aktualisiert
