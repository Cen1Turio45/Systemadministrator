# Outlook Troubleshooting

Schnellhilfe für das klassische Outlook unter Windows. Das passende Problem auswählen und nach jedem Schritt testen. Sobald Outlook wieder funktioniert, keine weiteren Änderungen vornehmen.

## Schnellübersicht

| Problem | Zuerst prüfen | Danach |
| --- | --- | --- |
| Outlook startet nicht oder hängt | Prozesse beenden und abgesicherten Modus testen | Testprofil erstellen, dann Office reparieren |
| Anmeldung oder Lizenz fehlerhaft | Office-Konto und Aktivierung prüfen | Anmeldedaten bereinigen und Lizenz kontrollieren |
| Kein Versand oder Empfang | Internet, Offline-Modus und Postausgang prüfen | Konto- und Serverdaten kontrollieren |
| PST-Datei fehlerhaft | Datei suchen und Original sichern | Kopie reparieren oder Archiv anlegen |
| Outlook langsam oder fehlerhafte Anzeige | Add-ins deaktivieren | Grafik, Cache und Datendateigröße prüfen |

## Outlook startet nicht oder hängt beim Profil

### Anleitung

1. PC neu starten. Danach im Task-Manager alle Prozesse `OUTLOOK.EXE` beenden und erneut testen.
2. Mit `Win + R` und `outlook.exe /safe` abgesichert starten. Funktioniert das, unter `Datei > Optionen > Add-Ins` Drittanbieter-Add-ins deaktivieren.
3. Startet Outlook nicht, unter `Systemsteuerung > Mail (Microsoft Outlook) > Profile anzeigen` ein leeres Profil `Test` anlegen und damit starten.
4. Scheitert das Testprofil, unter `Einstellungen > Apps > Microsoft 365 > Ändern` erst die Schnell- und danach die Onlinereparatur ausführen.

### Was bringt das?

Die Reihenfolge prüft Prozesse, Add-ins, Outlook-Profil und Office-Installation.

### Wie geht es weiter?

Startet das Testprofil, ein neues Profil mit dem echten Konto erstellen. Hilft auch die Onlinereparatur nicht, Fehler dokumentieren und eskalieren.

## Anmeldung oder Lizenz fehlerhaft

### Anleitung

1. In Outlook oder einer anderen Office-App `Datei > Konto` öffnen und angemeldetes Konto sowie Aktivierungsstatus prüfen.
2. Mit dem lizenzierten Geschäfts- oder Schulkonto neu anmelden und MFA bestätigen.
3. Im Microsoft 365 Admin Center prüfen, ob dem Benutzer eine passende Lizenz zugewiesen ist.
4. Bei einer Anmeldeschleife veraltete Office-Einträge unter `Systemsteuerung > Anmeldeinformationsverwaltung > Windows-Anmeldeinformationen` entfernen und neu anmelden.

### Was bringt das?

Damit werden falsches Konto, fehlende Lizenz und veraltete Anmeldedaten ausgeschlossen.

### Wie geht es weiter?

Bleibt der Fehler, Kontostatus, MFA und Service Health prüfen. Registry nicht auf Verdacht verändern.

## E-Mails werden nicht gesendet oder empfangen

### Anleitung

1. Internetverbindung, Microsoft 365 Service Health beziehungsweise Providerstatus prüfen.
2. Kontrollieren, ob `Offline arbeiten` aktiv ist oder Nachrichten im Postausgang hängen.
3. Unter `Systemsteuerung > Mail (Microsoft Outlook) > E-Mail-Konten` das betroffene Konto und die Anmeldedaten prüfen.
4. Bei IMAP unter `Weitere Einstellungen > Erweitert` Ports, Verschlüsselung und SMTP-Authentifizierung mit den Providerangaben vergleichen.

### Was bringt das?

Die Prüfung grenzt Verbindungs-, Server-, Anmelde- und Konfigurationsfehler ein.

### Wie geht es weiter?

Erneut testen. Bleibt der Fehler, Meldung und Zeitpunkt dokumentieren und an Provider oder Administrator eskalieren.

## PST-Datei fehlt, ist beschädigt oder zu groß

### Anleitung

1. Outlook schließen, Speicherort prüfen und die gefundene PST-Datei sichern. Bei POP kann sie die einzige Kopie der E-Mails enthalten.
2. Wurde sie nur verschoben, über `Datei > Öffnen und exportieren > Outlook-Datendatei öffnen` erneut einbinden.
3. Ist sie beschädigt, eine Kopie mit `SCANPST.EXE` reparieren. Das Original unverändert lassen.
4. Ist sie zu groß, über `Kontoeinstellungen > Datendateien > Hinzufügen` eine Archiv-PST erstellen und ältere E-Mails in kleinen Blöcken verschieben.

### Was bringt das?

Die Datei wird eingebunden, auf einer Kopie repariert oder durch ein Archiv entlastet.

### Wie geht es weiter?

Inhalte prüfen und PST-Dateien sichern. Fehlt die Datei oder scheitert die Reparatur, Datenrettung eskalieren.

## Outlook ist langsam oder zeigt Darstellungsfehler

### Anleitung

1. Unter `Datei > Optionen > Add-Ins` nicht benötigte Drittanbieter-Add-ins testweise deaktivieren.
2. Bei Darstellungsfehlern unter `Datei > Optionen > Erweitert > Anzeige` Hardwaregrafikbeschleunigung und Animationen testweise ausschalten, sofern verfügbar.
3. Bei Exchange den Cache-Modus prüfen und den Offlinezeitraum passend zu Gerät und Postfachgröße einstellen.
4. Outlook neu starten und nur Einstellungen beibehalten, die tatsächlich helfen.

### Was bringt das?

Die Schritte reduzieren Belastungen durch Add-ins, Grafik und große lokale Postfachkopien.

### Wie geht es weiter?

Bleibt Outlook langsam, OST-/PST-Größe, Systemleistung und Netzwerk prüfen. Externe Bilder nicht pauschal automatisch laden.

## Wichtige Sicherheitsregeln

- Ein altes Profil erst löschen, wenn alle lokalen Daten gesichert und das neue Profil vollständig getestet wurde.
- Bei POP die PST-Datei immer sichern; lokale Nachrichten werden nicht automatisch vom Server wiederhergestellt.
- PST-Reparaturen nur an einer Kopie durchführen und dafür den Windows Defender nicht deaktivieren.
- Passwörter und MFA-Codes niemals im Ticket dokumentieren.
