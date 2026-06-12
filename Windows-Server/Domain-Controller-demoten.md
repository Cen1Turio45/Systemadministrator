# Domain Controller demoten

## Ziel

Kurze Checkliste zum Herunterstufen oder Bereinigen eines Domain Controllers.

## Checkliste Online-Demotion

- Prüfen, ob weitere funktionierende Domain Controller vorhanden sind.
- Prüfen, ob FSMO-Rollen verschoben werden müssen.
- DNS-Rolle und weitere Dienste berücksichtigen.
- Server Manager öffnen und `Remove Roles and Features` starten.
- Rolle `Active Directory Domain Services` entfernen.
- `Demote this domain controller` auswählen.
- `Force removal` nur verwenden, wenn es wirklich erforderlich ist.
- Lokalen Administratorzugang für den Server setzen.
- Demotion abschließen und Neustart durchführen.

## Checkliste Bereinigung

- Alten DC aus `Active Directory Users and Computers` entfernen, falls er nicht mehr zurückkommt.
- `Active Directory Sites and Services` öffnen.
- Veraltete Serverreferenzen entfernen.
- DNS Manager öffnen.
- Veraltete SRV- und Host-Einträge des alten DC entfernen.
- Replikation und Anmeldung über verbleibende DCs prüfen.
