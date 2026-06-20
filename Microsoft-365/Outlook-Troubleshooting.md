# Outlook Troubleshooting

Kurzanleitungen für das klassische Outlook unter Windows. Das passende Problem auswählen, die Schritte der Reihe nach durchführen und nach jedem Schritt testen. Sobald Outlook wieder funktioniert, aufhören und das Ergebnis im Ticket dokumentieren.

## Outlook-Konto hinzufügen

### Microsoft 365 oder Exchange

1. In Outlook `Datei > Konto hinzufügen` öffnen.
2. E-Mail-Adresse eingeben und `Verbinden` auswählen.
3. Mit dem Geschäfts- oder Schulkonto anmelden und MFA bestätigen.
4. Outlook neu starten.
5. Testnachricht senden sowie Empfang und Ordnersynchronisierung prüfen.

Bei Microsoft 365 oder Exchange keine IMAP-Daten eintragen, solange die automatische Einrichtung vorgesehen ist. Funktioniert sie nicht, E-Mail-Adresse, Internetverbindung, Lizenz und Microsoft-365-Anmeldung prüfen.

### IMAP-Konto

1. Servernamen, Ports und Verschlüsselung aus der Provider- oder Kundendokumentation bereithalten.
2. `Datei > Konto hinzufügen > Erweiterte Optionen` öffnen.
3. `Ich möchte mein Konto manuell einrichten` und anschließend `IMAP` auswählen.
4. Posteingangs- und Postausgangsserver exakt nach Providerangabe eintragen.
5. Falls gefordert, SMTP-Authentifizierung mit denselben Zugangsdaten aktivieren.
6. Senden und Empfangen testen.

Häufige Werte sind IMAP `993` mit SSL/TLS sowie SMTP `465` mit SSL/TLS oder `587` mit STARTTLS. Die Angaben des Providers haben immer Vorrang.

## Outlook startet nicht

1. Computer neu starten und Outlook erneut öffnen.
2. Falls Outlook weiterhin nicht startet, mit `Strg + Umschalt + Esc` den Task-Manager öffnen.
3. Unter `Details` alle Prozesse `OUTLOOK.EXE` beenden.
4. Outlook erneut starten.
5. Bleibt der Fehler bestehen, mit der Kurzanleitung **Outlook im abgesicherten Modus testen** fortfahren.

## Outlook im abgesicherten Modus testen

1. `Win + R` drücken.
2. Folgenden Befehl ausführen:

```text
outlook.exe /safe
```

3. Startet Outlook, `Datei > Optionen > Add-Ins` öffnen.
4. Bei `Verwalten: COM-Add-Ins` auf `Los` klicken.
5. Drittanbieter-Add-ins deaktivieren und Outlook normal neu starten.
6. Benötigte Add-ins einzeln wieder aktivieren, bis der Verursacher gefunden ist.

Besprechungs-, Fernwartungs- und Antiviren-Add-ins können Startprobleme verursachen. Das Microsoft-Exchange-Add-in nicht pauschal deaktivieren.

## Outlook hängt bei „Profil wird geladen“

1. Outlook schließen.
2. `Systemsteuerung > Mail (Microsoft Outlook) > Profile anzeigen` öffnen.
3. Prüfen, ob unnötige oder doppelte Profile vorhanden sind, aber noch nichts löschen.
4. `Hinzufügen` wählen und ein leeres Profil mit dem Namen `Test` erstellen.
5. Die Kontoeinrichtung abbrechen und, falls angeboten, Outlook ohne E-Mail-Konto verwenden.
6. Bei `Zu verwendendes Profil bestätigen` das Profil `Test` auswählen.
7. Outlook starten.

Startet Outlook mit dem Testprofil, liegt das Problem wahrscheinlich am alten Profil oder dessen Datendatei. Ein neues Profil mit dem echten Konto erstellen und vollständig testen. Das alte Profil erst entfernen, wenn alle benötigten E-Mails und Datendateien vorhanden oder gesichert sind.

Eine OST- oder PST-Datei mit 20–30 GB ist allein kein Grund, ein Profil zu löschen. Große Dateien können Outlook jedoch verlangsamen und sollten genauer geprüft werden.

## Microsoft-365-Anmeldung erscheint immer wieder

1. Outlook und alle anderen Office-Programme schließen.
2. In einer funktionierenden Office-App unter `Datei > Konto` kontrollieren, ob das richtige Konto angemeldet und Microsoft 365 aktiviert ist.
3. `Systemsteuerung > Anmeldeinformationsverwaltung > Windows-Anmeldeinformationen` öffnen.
4. Veraltete Einträge zu Outlook, Office oder Microsoft 365 nur entfernen, wenn Benutzername, Passwort und MFA verfügbar sind.
5. Outlook öffnen und neu anmelden.

Keine unbekannten Registry-Einträge auf Verdacht ändern. Bleibt die Anmeldeschleife bestehen, Lizenz, MFA, Kontostatus und Microsoft 365 Service Health prüfen oder eskalieren.

## Outlook-Lizenz ist nicht aktiviert

1. In Outlook oder einer anderen Office-App `Datei > Konto` öffnen.
2. Unter `Produktinformationen` den Aktivierungsstatus prüfen.
3. Abmelden und mit dem lizenzierten Geschäfts- oder Schulkonto erneut anmelden.
4. Im Microsoft 365 Admin Center kontrollieren, ob dem Benutzer eine passende Lizenz zugewiesen ist.
5. Office-App neu starten und Aktivierung erneut prüfen.

## E-Mails werden nicht gesendet oder empfangen

1. Internetverbindung und Microsoft 365 Service Health beziehungsweise Providerstatus prüfen.
2. In Outlook kontrollieren, ob `Offline arbeiten` aktiviert ist und ob Nachrichten im Postausgang hängen.
3. `Systemsteuerung > Mail (Microsoft Outlook) > E-Mail-Konten` öffnen.
4. Betroffenes Konto auswählen und E-Mail-Adresse, Benutzername und Serverdaten prüfen.
5. Unter `Weitere Einstellungen > Erweitert` Ports und Verschlüsselung mit der Providerdokumentation vergleichen.
6. SMTP-Authentifizierung prüfen und anschließend Senden sowie Empfangen testen.

Bei Microsoft 365 oder Exchange zusätzlich Lizenz, Anmeldung und Postfachstatus prüfen. Passwörter und MFA-Codes niemals im Ticket notieren.

## Outlook-Profil neu erstellen

1. Outlook schließen und `Systemsteuerung > Mail (Microsoft Outlook) > Profile anzeigen` öffnen.
2. Vorher prüfen, ob POP-Konten oder PST-Dateien verwendet werden.
3. `Hinzufügen` wählen und ein neues Profil erstellen.
4. E-Mail-Konto einrichten und Outlook mit dem neuen Profil starten.
5. Senden, Empfangen, Kalender, Kontakte und benötigte Ordner prüfen.
6. Erst nach erfolgreichem Test das neue Profil als Standard festlegen.
7. Altes Profil nur entfernen, wenn alle lokalen Daten gesichert wurden.

Bei Exchange und IMAP lassen sich serverseitig synchronisierte Daten erneut laden. Lokale POP-Nachrichten oder PST-Inhalte werden nicht automatisch wiederhergestellt.

## Microsoft 365 reparieren

1. `Einstellungen > Apps > Installierte Apps > Microsoft 365 > Ändern` öffnen.
2. `Schnellreparatur` ausführen und Outlook testen.
3. Falls der Fehler bleibt, `Onlinereparatur` ausführen.
4. Nach der Onlinereparatur Office gegebenenfalls erneut aktivieren und Outlook testen.

Die Onlinereparatur benötigt eine Internetverbindung und dauert länger als die Schnellreparatur.

## PST-Datei wurde verschoben oder nicht gefunden

1. Fehlermeldung und erwarteten Dateipfad notieren.
2. Prüfen, ob die PST-Datei verschoben, umbenannt oder gelöscht wurde.
3. Gefundene PST-Datei zuerst sichern und danach über `Datei > Öffnen und exportieren > Outlook-Datendatei öffnen` einbinden.
4. Bei einem IMAP- oder Exchange-Konto kann ein neues Profil erstellt und der Serverbestand neu synchronisiert werden.
5. Bei einem POP-Konto nicht vorschnell das Profil löschen: Die PST-Datei kann die einzige Kopie der E-Mails enthalten.

Ist die PST-Datei gelöscht und nicht gesichert, Wiederherstellung eskalieren und möglichst keine weiteren Daten auf das betroffene Laufwerk schreiben.

## Beschädigte PST-Datei reparieren

1. Outlook schließen.
2. Eine Kopie der PST-Datei erstellen und das Original unverändert sichern.
3. `SCANPST.EXE` über die Windows-Suche oder im Microsoft-Office-Installationsordner öffnen.
4. Ausschließlich die Arbeitskopie auswählen und prüfen beziehungsweise reparieren.
5. Reparierte Kopie in Outlook öffnen und Inhalt kontrollieren.

Nicht am einzigen Original arbeiten und den Windows Defender für die Reparatur nicht deaktivieren. Wenn `SCANPST.EXE` scheitert oder wichtige Daten fehlen, eskalieren.

## PST-Datei ist zu groß: Archiv anlegen

1. Vor Änderungen eine Datensicherung erstellen.
2. In Outlook `Datei > Kontoeinstellungen > Kontoeinstellungen > Datendateien` öffnen.
3. `Hinzufügen` wählen und eine neue Outlook-Datendatei mit einem eindeutigen Namen, zum Beispiel `Archiv-2026.pst`, erstellen.
4. Im neuen Archiv passende Ordner wie `Posteingang` und `Gesendet` anlegen.
5. Ältere E-Mails in kleinen Blöcken verschieben und zwischendurch kontrollieren.

Das Verschieben großer Datenmengen kann lange dauern. Die Archiv-PST danach in die reguläre Datensicherung aufnehmen.

## Outlook läuft langsam oder zeigt Darstellungsfehler

1. Nicht benötigte Drittanbieter-Add-ins über `Datei > Optionen > Add-Ins` deaktivieren.
2. Bei Darstellungsfehlern unter `Datei > Optionen > Erweitert > Anzeige` die Hardwaregrafikbeschleunigung testweise deaktivieren, sofern die Option vorhanden ist.
3. Nicht benötigte Animationen testweise ausschalten.
4. Bei Exchange unter `Datei > Kontoeinstellungen` prüfen, ob der Exchange-Cache-Modus aktiviert ist.
5. Den Offlinezeitraum nur so groß wählen, wie es Gerät, Postfachgröße und Unternehmensvorgabe erlauben, danach Outlook neu starten.

Das automatische Herunterladen externer Bilder nicht pauschal aktivieren. Die Sperre schützt vor Tracking und sollte nur nach Sicherheitsvorgabe geändert werden.

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
