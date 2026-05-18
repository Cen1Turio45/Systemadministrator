# Outlook startet nicht: Profil und Anmeldedaten prüfen

## Ausgangslage

Outlook lädt beim Start Daten und das Benutzerprofil, öffnet sich danach aber nicht vollständig. Der Benutzer kann Outlook dadurch nicht normal verwenden.

## Ziel

Outlook soll wieder normal starten, ohne dass direkt ein neues Windows-Profil oder eine komplette Office-Neuinstallation erforderlich ist.

## Symptome

- Outlook bleibt beim Laden hängen.
- Outlook zeigt kurz das Profil oder den Startvorgang, öffnet sich aber nicht.
- Der Benutzer kann nicht auf E-Mails, Kalender oder Kontakte zugreifen.
- Das Problem kann durch beschädigte Add-ins, gespeicherte Anmeldedaten oder ein fehlerhaftes Outlook-Profil verursacht werden.

## Vorgehen

### 1. Outlook im abgesicherten Modus starten

Zuerst wird geprüft, ob Outlook ohne Add-ins starten kann.

1. `Win + R` drücken.
2. Folgenden Befehl ausführen:

```text
outlook.exe /safe
```

3. Prüfen, ob Outlook im abgesicherten Modus startet.
4. Outlook wieder schließen.
5. Outlook normal starten.
6. Benutzer einmal abmelden und erneut anmelden.
7. Outlook erneut normal testen.

Wenn Outlook danach wieder funktioniert, lag das Problem wahrscheinlich an einem temporären Startproblem oder an einem Add-in.

### 2. Gespeicherte Anmeldedaten prüfen

Wenn Outlook weiterhin nicht startet, werden die gespeicherten Windows-Anmeldeinformationen geprüft.

1. Systemsteuerung öffnen.
2. `Anmeldeinformationsverwaltung` öffnen.
3. Windows-Anmeldeinformationen prüfen.
4. Einträge suchen, die zu Outlook, Office, Microsoft 365 oder Exchange gehören.
5. Vor dem Löschen prüfen, ob die notwendigen Daten vorhanden sind:

- Benutzername
- E-Mail-Adresse
- Passwort
- ggf. MFA- oder Anmeldeinformationen nach Unternehmensvorgabe

6. Relevante gespeicherte Anmeldeinformationen entfernen.
7. Outlook erneut öffnen.
8. Zugangsdaten neu eingeben und Anmeldung testen.

Dieser Schritt hilft häufig, wenn Outlook mit alten oder beschädigten Credentials arbeitet.

### 3. Outlook-Mailprofil prüfen

Wenn auch die Anmeldeinformationen nicht helfen, wird das Outlook-Profil geprüft.

1. Systemsteuerung öffnen.
2. `Mail` öffnen.
3. `Profile anzeigen` auswählen.
4. Vor Änderungen prüfen, ob die notwendigen Anmeldedaten vorhanden sind.
5. Bestehendes Profil prüfen oder entfernen.
6. Neues Outlook-Profil erstellen.
7. E-Mail-Konto erneut hinzufügen.
8. Outlook mit dem neuen Profil starten.

Ein neues Outlook-Profil kann viele Probleme beheben, wenn lokale Profildaten beschädigt sind.

## Erwartetes Ergebnis

Mit diesen drei Schritten lassen sich viele typische Outlook-Startprobleme beheben:

1. Start im abgesicherten Modus
2. gespeicherte Anmeldeinformationen bereinigen
3. Outlook-Profil neu erstellen

In vielen Fällen reicht einer dieser Schritte aus, damit Outlook wieder normal startet.

## Eskalation

Das Problem sollte eskaliert werden, wenn:

- Outlook auch mit neuem Profil nicht startet
- mehrere Benutzer betroffen sind
- Exchange oder Microsoft 365 Service Health Auffälligkeiten zeigt
- Fehlermeldungen auf ein serverseitiges Problem hinweisen
- lokale Office-Reparatur oder Neuinstallation notwendig wird

## Dokumentation im Ticket

Im Ticket sollten folgende Punkte festgehalten werden:

- betroffener Benutzer
- Gerät und Windows-Version
- Outlook-/Office-Version
- Zeitpunkt des Problems
- Start im abgesicherten Modus getestet: ja/nein
- Anmeldeinformationen geprüft oder gelöscht: ja/nein
- Outlook-Profil neu erstellt: ja/nein
- Ergebnis nach jedem Schritt
- ggf. Fehlermeldungen oder Screenshots

## Beispiel für eine gute Ticketnotiz

```text
Problem:
Outlook lädt das Benutzerprofil, öffnet sich aber nicht vollständig.

Durchgeführt:
- Outlook mit outlook.exe /safe gestartet.
- Outlook danach geschlossen und normal erneut geöffnet.
- Benutzer ab- und angemeldet.
- Gespeicherte Office-/Outlook-Anmeldeinformationen geprüft.
- Outlook-Mailprofil in der Systemsteuerung geprüft.

Ergebnis:
Outlook startet nach Bereinigung der Anmeldeinformationen wieder normal.

Nächster Schritt:
Ticket schließen, falls Benutzer keine weiteren Probleme meldet.
```
