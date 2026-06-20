# Outlook Troubleshooting

Schnellhilfe für das klassische Outlook unter Windows. In der Übersicht auf das passende Problem klicken. Nach jedem Schritt testen und aufhören, sobald Outlook wieder funktioniert.

## Schnellübersicht

- [Outlook startet nicht oder hängt](#outlook-startet)
- [Anmeldung oder Lizenz fehlerhaft](#anmeldung-lizenz)
- [Kein Versand oder Empfang](#senden-empfangen)
- [PST-Datei fehlerhaft](#pst-datei)
- [Outlook langsam oder fehlerhafte Anzeige](#outlook-langsam)

<a id="outlook-startet"></a>
## Outlook startet nicht oder hängt beim Profil

<a id="outlook-startet-zuerst"></a>
### Zuerst prüfen

1. PC neu starten. Danach im Task-Manager alle Prozesse `OUTLOOK.EXE` beenden und erneut testen.
2. Mit `Win + R` und `outlook.exe /safe` abgesichert starten. Funktioniert das, unter `Datei > Optionen > Add-Ins` Drittanbieter-Add-ins deaktivieren.

<a id="outlook-startet-danach"></a>
### Falls das nicht hilft

3. Unter `Systemsteuerung > Mail (Microsoft Outlook) > Profile anzeigen` ein leeres Profil `Test` anlegen und damit starten.
4. Scheitert das Testprofil, unter `Einstellungen > Apps > Microsoft 365 > Ändern` erst die Schnell- und danach die Onlinereparatur ausführen.

<a id="anmeldung-lizenz"></a>
## Anmeldung oder Lizenz fehlerhaft

<a id="anmeldung-lizenz-zuerst"></a>
### Zuerst prüfen

1. In Outlook oder einer anderen Office-App `Datei > Konto` öffnen und angemeldetes Konto sowie Aktivierungsstatus prüfen.
2. Mit dem lizenzierten Geschäfts- oder Schulkonto neu anmelden und MFA bestätigen.

<a id="anmeldung-lizenz-danach"></a>
### Falls das nicht hilft

3. Im Microsoft 365 Admin Center prüfen, ob dem Benutzer eine passende Lizenz zugewiesen ist.
4. Bei einer Anmeldeschleife veraltete Office-Einträge unter `Systemsteuerung > Anmeldeinformationsverwaltung > Windows-Anmeldeinformationen` entfernen und neu anmelden.

<a id="senden-empfangen"></a>
## E-Mails werden nicht gesendet oder empfangen

<a id="senden-empfangen-zuerst"></a>
### Zuerst prüfen

1. Internetverbindung, Microsoft 365 Service Health beziehungsweise Providerstatus prüfen.
2. Kontrollieren, ob `Offline arbeiten` aktiv ist oder Nachrichten im Postausgang hängen.

<a id="senden-empfangen-danach"></a>
### Falls das nicht hilft

3. Unter `Systemsteuerung > Mail (Microsoft Outlook) > E-Mail-Konten` das betroffene Konto und die Anmeldedaten prüfen.
4. Bei IMAP unter `Weitere Einstellungen > Erweitert` Ports, Verschlüsselung und SMTP-Authentifizierung mit den Providerangaben vergleichen.

<a id="pst-datei"></a>
## PST-Datei fehlt, ist beschädigt oder zu groß

<a id="pst-datei-zuerst"></a>
### Zuerst prüfen

1. Outlook schließen, Speicherort prüfen und die gefundene PST-Datei sichern. Bei POP kann sie die einzige Kopie der E-Mails enthalten.

<a id="pst-datei-danach"></a>
### Passende Maßnahme

2. **Verschoben:** Über `Datei > Öffnen und exportieren > Outlook-Datendatei öffnen` erneut einbinden.
3. **Beschädigt:** Eine Kopie mit `SCANPST.EXE` reparieren und das Original unverändert lassen.
4. **Zu groß:** Über `Kontoeinstellungen > Datendateien > Hinzufügen` eine Archiv-PST erstellen und ältere E-Mails in kleinen Blöcken verschieben.

<a id="outlook-langsam"></a>
## Outlook ist langsam oder zeigt Darstellungsfehler

<a id="outlook-langsam-zuerst"></a>
### Zuerst prüfen

1. Unter `Datei > Optionen > Add-Ins` nicht benötigte Drittanbieter-Add-ins testweise deaktivieren.
2. Bei Darstellungsfehlern unter `Datei > Optionen > Erweitert > Anzeige` Hardwaregrafikbeschleunigung und Animationen testweise ausschalten, sofern verfügbar.

<a id="outlook-langsam-danach"></a>
### Falls das nicht hilft

3. Bei Exchange den Cache-Modus prüfen und den Offlinezeitraum passend zu Gerät und Postfachgröße einstellen.
4. Outlook neu starten und nur Einstellungen beibehalten, die tatsächlich helfen.

## Wichtige Sicherheitsregeln

- Ein altes Profil erst löschen, wenn alle lokalen Daten gesichert und das neue Profil vollständig getestet wurde.
- Bei POP die PST-Datei immer sichern; lokale Nachrichten werden nicht automatisch vom Server wiederhergestellt.
- PST-Reparaturen nur an einer Kopie durchführen und dafür den Windows Defender nicht deaktivieren.
- Passwörter und MFA-Codes niemals im Ticket dokumentieren.
