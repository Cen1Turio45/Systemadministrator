# Outlook: E-Mail-Konto hinzufügen

## Ziel

Ein zusätzliches E-Mail-Konto soll in Outlook eingerichtet werden.

## Ausgangslage

Ein Benutzer benötigt ein weiteres Postfach oder ein externes E-Mail-Konto in Outlook. Je nach Anbieter wird das Konto automatisch über Exchange/Microsoft 365 erkannt oder manuell per IMAP/POP3 eingerichtet.

## Vorbereitung

Vor der Einrichtung prüfen:

- E-Mail-Adresse
- Benutzername
- Passwort
- Kontotyp, z. B. Exchange, IMAP oder POP3
- Posteingangsserver
- Postausgangsserver
- Ports und Verschlüsselung

Zugangsdaten sollten nur über freigegebene und sichere Wege verwendet werden.

## Konto manuell hinzufügen

1. Systemsteuerung öffnen.
2. `Mail` öffnen.
3. `E-Mail-Konten` auswählen.
4. `Neu` auswählen.
5. Manuelle Konfiguration auswählen.
6. Kontotyp auswählen, z. B. `IMAP`.
7. Serverdaten eintragen.
8. Benutzername und Passwort eintragen.
9. Weitere Einstellungen öffnen.
10. Postausgangsserver-Authentifizierung aktivieren, falls erforderlich.
11. Verschlüsselung und Ports setzen.
12. Einrichtung testen.
13. Outlook schließen und neu starten.

## Beispielwerte

Die Werte hängen vom Provider ab. Typische Beispiele:

| Dienst | Server | Port | Verschlüsselung |
| --- | --- | --- | --- |
| IMAP | `imap.example.com` | `993` | SSL/TLS |
| POP3 | `pop3.example.com` | `995` | SSL/TLS |
| SMTP | `smtp.example.com` | `465` | SSL/TLS |

Die tatsächlichen Werte müssen aus der Kundendokumentation oder vom Provider übernommen werden.

## Exchange-Konto

Bei Exchange oder Microsoft 365 reicht häufig die E-Mail-Adresse. Outlook ruft die weiteren Einstellungen automatisch ab, wenn Autodiscover korrekt funktioniert.

## Fehlerbehebung

Wenn die Einrichtung nicht funktioniert:

- Benutzername prüfen
- Passwort prüfen
- Kontotyp prüfen
- Ports und Verschlüsselung prüfen
- Postausgangsserver-Authentifizierung prüfen
- Outlook neu starten

## Nachkontrolle

Prüfen:

- Konto erscheint links in Outlook.
- Senden funktioniert.
- Empfangen funktioniert.
- Ordner werden synchronisiert.
- Benutzer kann Outlook nach Neustart normal öffnen.

## Dokumentation im Ticket

Festhalten:

- Kontoart
- Provider oder Exchange/Microsoft 365
- Einrichtung erfolgreich
- Senden/Empfangen getestet
- Besonderheiten bei Ports oder Verschlüsselung
