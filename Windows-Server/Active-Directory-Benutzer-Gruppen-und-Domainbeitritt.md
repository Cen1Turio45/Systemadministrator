# Active Directory: Benutzer, Gruppen und Domainbeitritt

## Ziel

Diese Anleitung beschreibt typische Active-Directory-Aufgaben im Support: Computer der Domäne beitreten lassen, Benutzer anlegen, Passwörter zurücksetzen, Accounts entsperren und Gruppen pflegen.

## Computer der Domäne beitreten lassen

### Vorprüfung

1. Prüfen, ob der Computername bereits in Active Directory existiert.
2. DNS des Clients auf den Domain Controller setzen.
3. Netzwerkverbindung zum Domain Controller prüfen.
4. Uhrzeit und Zeitzone prüfen, da Kerberos zeitkritisch ist.

### Domainbeitritt

1. Windows-Einstellungen öffnen.
2. `Konten > Auf Arbeits- oder Schulkonto zugreifen` öffnen.
3. `Verbinden` auswählen.
4. Option für lokale Active-Directory-Domäne auswählen.
5. Domänenname eintragen.
6. Domänenberechtigte Zugangsdaten eingeben.
7. Gerät neu starten.
8. In Active Directory prüfen, ob das Computerkonto sichtbar ist.

## Neuen Benutzer anlegen

1. `Active Directory Users and Computers` öffnen.
2. Passende OU auswählen.
3. Rechtsklick > `Neu > Benutzer`.
4. Name, Anmeldename und weitere Pflichtfelder eintragen.
5. Temporäres Passwort setzen.
6. Option `Benutzer muss Kennwort bei der nächsten Anmeldung ändern` aktivieren.
7. Benutzer erstellen.
8. Eigenschaften öffnen und sinnvolle Zusatzinformationen pflegen.
9. Gruppenmitgliedschaften hinzufügen.

## Passwort zurücksetzen

1. Benutzer in Active Directory suchen.
2. Rechtsklick auf den Benutzer.
3. `Kennwort zurücksetzen` auswählen.
4. Neues temporäres Passwort setzen.
5. `Benutzer muss Kennwort bei der nächsten Anmeldung ändern` aktivieren.
6. Benutzer über den sicheren Übergabeweg informieren.

## Gesperrten Account entsperren

1. Benutzer in Active Directory öffnen.
2. Eigenschaften aufrufen.
3. Tab `Account` öffnen.
4. Haken bei `Unlock account` setzen.
5. Übernehmen und Benutzer erneut testen lassen.

## Account deaktivieren

1. Benutzer in Active Directory suchen.
2. Rechtsklick auf den Benutzer.
3. `Account deaktivieren` auswählen.
4. Falls erforderlich Gruppen, Postfach, Geräte und Zugriffe separat nach Prozess behandeln.

## Gruppen erstellen

1. Passende OU auswählen.
2. Rechtsklick > `Neu > Gruppe`.
3. Gruppennamen nach Namenskonvention vergeben.
4. Gruppentyp festlegen:

| Typ | Zweck |
| --- | --- |
| Sicherheitsgruppe | Berechtigungen auf Ressourcen |
| Verteilergruppe | E-Mail-Verteilung |

5. Gruppe erstellen.
6. Mitglieder hinzufügen.

## Gute Praxis

- Berechtigungen möglichst über Gruppen vergeben, nicht direkt auf einzelne Benutzer.
- Änderungen im Ticket dokumentieren.
- Bei neuen Benutzern Gruppen anhand einer vergleichbaren Rolle prüfen.
- Bei Account-Problemen immer zwischen Passwortproblem, Sperrung und Berechtigungsproblem unterscheiden.
