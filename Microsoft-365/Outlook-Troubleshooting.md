# Outlook Troubleshooting

Kurzanleitungen für das klassische Outlook unter Windows. Das passende Problem auswählen und die Schritte der Reihe nach durchführen. Sobald Outlook wieder funktioniert, keine weiteren Änderungen vornehmen.

## Outlook-Konto hinzufügen

### Anleitung: Microsoft 365 oder Exchange

1. In Outlook `Datei > Konto hinzufügen` öffnen.
2. E-Mail-Adresse eingeben und `Verbinden` auswählen.
3. Mit dem Geschäfts- oder Schulkonto anmelden und MFA bestätigen.
4. Outlook neu starten.
5. Testnachricht senden sowie Empfang und Ordnersynchronisierung prüfen.

### Was bringt das?

Outlook ruft die benötigten Microsoft-365- oder Exchange-Einstellungen automatisch ab. Dadurch müssen keine Server, Ports oder Verschlüsselungsmethoden von Hand eingetragen werden.

### Wie geht es weiter?

Funktioniert die Einrichtung nicht, E-Mail-Adresse, Internetverbindung, Lizenz und Microsoft-365-Anmeldung prüfen. Keine IMAP-Daten eintragen, solange für das Konto die automatische Exchange-Einrichtung vorgesehen ist.

## IMAP-Konto hinzufügen

### Anleitung

1. Servernamen, Ports und Verschlüsselung aus der Provider- oder Kundendokumentation bereithalten.
2. `Datei > Konto hinzufügen > Erweiterte Optionen` öffnen.
3. `Ich möchte mein Konto manuell einrichten` und danach `IMAP` auswählen.
4. Posteingangs- und Postausgangsserver exakt nach Providerangabe eintragen.
5. Falls gefordert, SMTP-Authentifizierung mit denselben Zugangsdaten aktivieren.
6. Senden und Empfangen testen.

### Was bringt das?

Die manuelle Einrichtung verbindet Outlook mit einem Konto, das nicht automatisch über Microsoft 365 oder Exchange erkannt wird.

### Wie geht es weiter?

Schlägt der Test fehl, Servernamen, Benutzername, Ports, Verschlüsselung und SMTP-Authentifizierung erneut vergleichen. Häufig werden IMAP `993` mit SSL/TLS sowie SMTP `465` mit SSL/TLS oder `587` mit STARTTLS verwendet. Die Providerangaben haben immer Vorrang.

## Outlook startet nicht

### Anleitung

1. Computer neu starten und Outlook erneut öffnen.
2. Falls Outlook weiterhin nicht startet, mit `Strg + Umschalt + Esc` den Task-Manager öffnen.
3. Unter `Details` alle Prozesse `OUTLOOK.EXE` beenden.
4. Outlook erneut starten.

### Was bringt das?

Der Neustart beendet festhängende Outlook- und Office-Prozesse. Das manuelle Beenden hilft, wenn Outlook unsichtbar im Hintergrund läuft und deshalb nicht noch einmal geöffnet werden kann.

### Wie geht es weiter?

Startet Outlook weiterhin nicht, als Nächstes den abgesicherten Modus testen. Erscheint eine konkrete Fehlermeldung, diese vor weiteren Änderungen im Ticket festhalten.

## Outlook im abgesicherten Modus testen

### Anleitung

1. `Win + R` drücken.
2. Folgenden Befehl ausführen:

```text
outlook.exe /safe
```

3. Startet Outlook, `Datei > Optionen > Add-Ins` öffnen.
4. Bei `Verwalten: COM-Add-Ins` auf `Los` klicken.
5. Drittanbieter-Add-ins deaktivieren und Outlook normal neu starten.
6. Benötigte Add-ins einzeln wieder aktivieren, bis der Verursacher gefunden ist.

### Was bringt das?

Im abgesicherten Modus startet Outlook ohne die meisten Erweiterungen und individuellen Einstellungen. Startet es dort, verursacht wahrscheinlich ein Add-in oder eine angepasste Einstellung das Problem.

### Wie geht es weiter?

Das fehlerhafte Add-in deaktiviert lassen und bei Bedarf aktualisieren oder deinstallieren. Besprechungs-, Fernwartungs- und Antiviren-Add-ins sind mögliche Ursachen. Das Microsoft-Exchange-Add-in nicht pauschal deaktivieren. Startet auch der abgesicherte Modus nicht, das Outlook-Profil testen.

## Outlook hängt bei „Profil wird geladen“

### Anleitung

1. Outlook schließen.
2. `Systemsteuerung > Mail (Microsoft Outlook) > Profile anzeigen` öffnen.
3. Prüfen, ob unnötige oder doppelte Profile vorhanden sind, aber noch nichts löschen.
4. `Hinzufügen` wählen und ein leeres Profil mit dem Namen `Test` erstellen.
5. Die Kontoeinrichtung abbrechen und, falls angeboten, Outlook ohne E-Mail-Konto verwenden.
6. Bei `Zu verwendendes Profil bestätigen` das Profil `Test` auswählen.
7. Outlook starten.

### Was bringt das?

Das leere Testprofil trennt einen Outlook-Programmfehler von einem beschädigten Benutzerprofil. Startet Outlook damit, funktionieren die Anwendung und die grundlegende Office-Installation noch.

### Wie geht es weiter?

Startet das Testprofil, ein neues Profil mit dem echten Konto erstellen und vollständig prüfen. Das alte Profil erst entfernen, wenn alle benötigten E-Mails und Datendateien vorhanden oder gesichert sind. Eine OST- oder PST-Datei mit 20–30 GB ist allein kein Löschgrund. Startet auch das Testprofil nicht, Microsoft 365 reparieren.

## Microsoft-365-Anmeldung erscheint immer wieder

### Anleitung

1. Outlook und alle anderen Office-Programme schließen.
2. In einer funktionierenden Office-App unter `Datei > Konto` prüfen, ob das richtige Konto angemeldet und Microsoft 365 aktiviert ist.
3. `Systemsteuerung > Anmeldeinformationsverwaltung > Windows-Anmeldeinformationen` öffnen.
4. Veraltete Einträge zu Outlook, Office oder Microsoft 365 nur entfernen, wenn Benutzername, Passwort und MFA verfügbar sind.
5. Outlook öffnen und neu anmelden.

### Was bringt das?

Damit werden falsche oder veraltete Anmeldedaten ausgeschlossen. Outlook fordert beim nächsten Start aktuelle Zugangsdaten an und kann ein neues Anmeldetoken erstellen.

### Wie geht es weiter?

Bleibt die Anmeldeschleife bestehen, Lizenz, MFA, Kontostatus und Microsoft 365 Service Health prüfen. Keine unbekannten Registry-Einträge auf Verdacht ändern; notwendige Registry-Arbeiten eskalieren.

## Outlook-Lizenz ist nicht aktiviert

### Anleitung

1. In Outlook oder einer anderen Office-App `Datei > Konto` öffnen.
2. Unter `Produktinformationen` den Aktivierungsstatus prüfen.
3. Abmelden und mit dem lizenzierten Geschäfts- oder Schulkonto erneut anmelden.
4. Im Microsoft 365 Admin Center kontrollieren, ob dem Benutzer eine passende Lizenz zugewiesen ist.
5. Office-App neu starten und die Aktivierung erneut prüfen.

### Was bringt das?

Die Prüfung zeigt, ob Outlook wegen einer fehlenden, falschen oder nicht aktivierten Microsoft-365-Lizenz eingeschränkt ist.

### Wie geht es weiter?

Fehlt die Lizenz, muss sie durch einen Administrator zugewiesen werden. Ist sie vorhanden, aber Office bleibt inaktiv, Anmeldung und Internetverbindung prüfen und danach Microsoft 365 reparieren.

## E-Mails werden nicht gesendet oder empfangen

### Anleitung

1. Internetverbindung und Microsoft 365 Service Health beziehungsweise Providerstatus prüfen.
2. In Outlook kontrollieren, ob `Offline arbeiten` aktiviert ist und ob Nachrichten im Postausgang hängen.
3. `Systemsteuerung > Mail (Microsoft Outlook) > E-Mail-Konten` öffnen.
4. Betroffenes Konto auswählen und E-Mail-Adresse, Benutzername und Serverdaten prüfen.
5. Unter `Weitere Einstellungen > Erweitert` Ports und Verschlüsselung mit der Providerdokumentation vergleichen.
6. SMTP-Authentifizierung prüfen und anschließend Senden sowie Empfangen testen.

### Was bringt das?

Die Schritte grenzen Verbindungs-, Server- und Konfigurationsfehler voneinander ab. Der Test zeigt außerdem, ob nur der Versand, nur der Empfang oder das gesamte Konto betroffen ist.

### Wie geht es weiter?

Bei Microsoft 365 oder Exchange zusätzlich Lizenz, Anmeldung und Postfachstatus prüfen. Bei einem Providerkonto die bestätigten Serverdaten verwenden. Bleibt der Fehler bestehen, Fehlermeldung und Testzeitpunkt dokumentieren und an den Provider oder Microsoft-365-Administrator eskalieren.

## Outlook-Profil neu erstellen

### Anleitung

1. Outlook schließen und `Systemsteuerung > Mail (Microsoft Outlook) > Profile anzeigen` öffnen.
2. Prüfen, ob POP-Konten oder PST-Dateien verwendet werden, und lokale Daten zuerst sichern.
3. `Hinzufügen` wählen und ein neues Profil erstellen.
4. E-Mail-Konto einrichten und Outlook mit dem neuen Profil starten.
5. Senden, Empfangen, Kalender, Kontakte und benötigte Ordner prüfen.
6. Nach erfolgreichem Test das neue Profil als Standard festlegen.
7. Altes Profil nur entfernen, wenn alle lokalen Daten gesichert wurden.

### Was bringt das?

Ein neues Profil ersetzt beschädigte lokale Konto- und Profileinstellungen, ohne Outlook oder das gesamte Windows-Benutzerprofil neu installieren zu müssen.

### Wie geht es weiter?

Bei Exchange und IMAP die vollständige Serversynchronisierung abwarten. Lokale POP-Nachrichten und PST-Inhalte werden nicht automatisch wiederhergestellt und müssen gesichert beziehungsweise eingebunden werden. Hilft das neue Profil nicht, Microsoft 365 reparieren.

## Microsoft 365 reparieren

### Anleitung

1. `Einstellungen > Apps > Installierte Apps > Microsoft 365 > Ändern` öffnen.
2. `Schnellreparatur` ausführen und Outlook testen.
3. Falls der Fehler bleibt, `Onlinereparatur` ausführen.
4. Danach Office gegebenenfalls erneut aktivieren und Outlook testen.

### Was bringt das?

Die Schnellreparatur ersetzt beschädigte lokale Office-Dateien. Die Onlinereparatur installiert die Office-Komponenten umfassender neu und behebt dadurch tiefere Installationsfehler.

### Wie geht es weiter?

Für die Onlinereparatur Internetzugang und Zeit einplanen. Startet Outlook danach auch mit einem leeren Testprofil nicht, Fehlermeldungen dokumentieren und eskalieren.

## PST-Datei wurde verschoben oder nicht gefunden

### Anleitung

1. Fehlermeldung und erwarteten Dateipfad notieren.
2. Prüfen, ob die PST-Datei verschoben, umbenannt oder gelöscht wurde.
3. Eine gefundene PST-Datei zuerst sichern.
4. Danach `Datei > Öffnen und exportieren > Outlook-Datendatei öffnen` auswählen und die PST-Datei einbinden.
5. Outlook neu starten und die enthaltenen Ordner prüfen.

### Was bringt das?

Outlook erhält wieder den korrekten Verweis auf die lokale Datendatei. Durch die Sicherung bleibt vor weiteren Änderungen eine unveränderte Kopie erhalten.

### Wie geht es weiter?

Bei IMAP oder Exchange kann ein neues Profil erstellt und der Serverbestand neu synchronisiert werden. Bei POP nicht vorschnell das Profil löschen, weil die PST-Datei die einzige Kopie der E-Mails enthalten kann. Ist sie gelöscht und nicht gesichert, Datenrettung eskalieren und möglichst nichts mehr auf das betroffene Laufwerk schreiben.

## Beschädigte PST-Datei reparieren

### Anleitung

1. Outlook schließen.
2. Eine Kopie der PST-Datei erstellen und das Original unverändert sichern.
3. `SCANPST.EXE` über die Windows-Suche oder im Microsoft-Office-Installationsordner öffnen.
4. Ausschließlich die Arbeitskopie auswählen und prüfen beziehungsweise reparieren.
5. Die reparierte Kopie in Outlook öffnen und den Inhalt kontrollieren.

### Was bringt das?

`SCANPST.EXE` prüft die interne Struktur der Outlook-Datendatei und versucht beschädigte Ordner und Verweise wiederherzustellen. Das Original bleibt als Rückfallebene erhalten.

### Wie geht es weiter?

Fehlende oder beschädigte Elemente dokumentieren. Scheitert die Reparatur oder fehlen wichtige Daten, eskalieren. Nicht am einzigen Original arbeiten und den Windows Defender für die Reparatur nicht deaktivieren.

## PST-Datei ist zu groß: Archiv anlegen

### Anleitung

1. Vor Änderungen eine Datensicherung erstellen.
2. In Outlook `Datei > Kontoeinstellungen > Kontoeinstellungen > Datendateien` öffnen.
3. `Hinzufügen` wählen und beispielsweise `Archiv-2026.pst` erstellen.
4. Im Archiv passende Ordner wie `Posteingang` und `Gesendet` anlegen.
5. Ältere E-Mails in kleinen Blöcken verschieben und zwischendurch kontrollieren.

### Was bringt das?

Ältere Nachrichten werden aus der stark belegten Hauptdatei ausgelagert. Dadurch kann Outlook übersichtlicher und bei sehr großen Datendateien stabiler arbeiten.

### Wie geht es weiter?

Das Verschieben großer Datenmengen vollständig abwarten und Stichproben durchführen. Die Archiv-PST in die reguläre Datensicherung aufnehmen und ihren Speicherort dokumentieren.

## Outlook läuft langsam oder zeigt Darstellungsfehler

### Anleitung

1. Nicht benötigte Drittanbieter-Add-ins über `Datei > Optionen > Add-Ins` deaktivieren.
2. Bei Darstellungsfehlern unter `Datei > Optionen > Erweitert > Anzeige` die Hardwaregrafikbeschleunigung testweise deaktivieren, sofern die Option vorhanden ist.
3. Nicht benötigte Animationen testweise ausschalten.
4. Bei Exchange unter `Datei > Kontoeinstellungen` prüfen, ob der Exchange-Cache-Modus aktiviert ist.
5. Den Offlinezeitraum passend zu Gerät, Postfachgröße und Unternehmensvorgabe einstellen und Outlook neu starten.

### Was bringt das?

Die Änderungen reduzieren mögliche Belastungen durch Erweiterungen, Grafikdarstellung und sehr große lokale Postfachkopien. Durch einzelne Tests lässt sich erkennen, welche Einstellung tatsächlich hilft.

### Wie geht es weiter?

Nur wirksame Änderungen beibehalten und benötigte Add-ins wieder aktivieren. Das automatische Herunterladen externer Bilder nicht pauschal einschalten, da die Sperre vor Tracking schützt. Bleibt Outlook langsam, Größe der Datendateien, Systemleistung und Netzwerkverbindung prüfen.

## Wann eskalieren?

Eskalieren, wenn Outlook auch mit leerem Testprofil und nach der Office-Reparatur nicht startet, mehrere Benutzer betroffen sind, Microsoft 365 eine Störung meldet, eine PST-Datei fehlt oder beschädigt ist, oder unbekannte Registry-Änderungen beziehungsweise Spezialwerkzeuge erforderlich wären.

## Kurze Ticketnotiz

```text
Problem:
Outlook hängt beim Laden des Profils.

Durchgeführt:
- Laufende Outlook-Prozesse beendet.
- Abgesicherten Modus getestet.
- Add-ins geprüft.
- Leeres Testprofil gestartet.

Ergebnis:
Outlook startet mit dem Testprofil. Neues Benutzerprofil wird eingerichtet.
```
