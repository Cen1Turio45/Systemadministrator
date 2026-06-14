# LANCOM VPN-Verbindung ändern

## Ziel

Diese Anleitung beschreibt, wie eine bestehende LANCOM-VPN-Verbindung angepasst oder neu eingerichtet wird, wenn die Verbindung nicht mehr funktioniert.

## Ausgangslage

Eine bestehende VPN-Verbindung funktioniert nicht mehr oder muss auf neue Verbindungsdaten umgestellt werden. Vor Änderungen sollte die alte Konfiguration dokumentiert werden, damit sie bei Bedarf nachvollziehbar bleibt.

## Vorbereitung

Vor der Änderung prüfen:

- betroffener Benutzer
- bisheriges VPN-Profil
- neue Verbindungsdaten
- Gateway-Adresse oder DNS-Name
- Authentifizierungsart
- Fehlermeldung des VPN-Clients

## Vorgehen

1. VPN-Client öffnen.
2. Bestehendes Profil sichern oder dokumentieren.
3. Fehlerhaftes Profil entfernen, falls erforderlich.
4. Neues Profil hinzufügen.
5. Verbindungstyp auswählen, z. B. IPsec/IKEv2.
6. Profilname setzen.
7. Gateway-Adresse oder DNS-Namen eintragen.
8. Authentifizierungsdaten nach Vorgabe setzen.
9. IPsec-Zuweisung der privaten IP-Adresse prüfen.
10. Verbindung testen.
11. Zugriff auf interne Dienste testen.

## Typische Prüfpunkte

- richtiger Gateway-DNS-Name
- richtige Benutzer-ID
- korrekter Authentifizierungstyp
- erreichbares Zielnetz
- gültiger VPN-Client
- keine alte fehlerhafte Profilkonfiguration

## Eskalation

Eskalieren, wenn:

- mehrere Benutzer betroffen sind
- Gateway nicht erreichbar ist
- Authentifizierung fehlschlägt
- Firewall- oder Routingproblem vermutet wird

## Dokumentation im Ticket

Festhalten:

- altes Profil entfernt: ja/nein
- neues Profil erstellt: ja/nein
- Verbindungstest erfolgreich
- interne Dienste erreichbar: ja/nein
- Fehlermeldung, falls vorhanden
- nächste Schritte
