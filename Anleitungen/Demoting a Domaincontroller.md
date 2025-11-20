# Demoting a Server (Domain Controller)

<img width="861" height="493" alt="image" src="https://github.com/user-attachments/assets/232bcabb-53f6-4dc6-b922-41c1f615111b" />

<img width="901" height="537" alt="image" src="https://github.com/user-attachments/assets/a27305d2-2962-4ec2-a969-7aa009eabc78" />

<br></br>

## 1. Demoting the old server while it is still online

1. Server Manager öffnen.

2. „Manage“ auswählen und „Remove Roles and Features“ öffnen.

3. Sicherstellen, dass der richtige Server ausgewählt ist.

4. Die Rolle „Active Directory Domain Services“ abwählen.

5. Wenn der Server auch DNS-Server ist, sollte die DNS-Serverrolle zuvor entfernt werden.

6. Beim Validierungsfenster auf „Demote this domain controller“ klicken.

7. Optional: Nicht „Force removal“ aktivieren, außer es handelt sich um den letzten verbleibenden DC.

8. Neuen lokalen Administratorzugang anlegen (da der Server nach der Demotion kein DC mehr ist).

9. Mit „Next“ bestätigen und den Vorgang abschließen.

10. Der Server wird heruntergestuft, aus AD entfernt und anschließend neu gestartet. Danach ist es ein normaler Windows-Server.

<br></br>

## 2. Cleaning up Active Directory Sites and Services

1. „Active Directory Sites and Services“ öffnen.

2. Unter „Servers“ den alten DC suchen.

3. Rechtsklick auf den alten Servernamen und „Delete“ auswählen.

4. Bestätigen, um die alte Serverreferenz vollständig zu entfernen.

<br></br>

## 3. Demoting when the old server is gone

1. Der Server kann nicht mehr über den Server Manager bereinigt werden

2. Alle AD-Verweise müssen daher manuell entfernt werden.

3. Zuerst sicherstellen, dass alle FSMO-Rollen bereits auf einen funktionierenden DC übertragen wurden.

<br></br>

## 4. Move FSMO roles (falls notwendig)

1. Aus einem anderen, funktionierenden DC heraus die FSMO-Rollen verschieben.

2. Der alte DC muss hierfür nicht online sein.

<br></br>

## 5. Delete the orphaned DC from Active Directory

1. „Active Directory Users and Computers“ öffnen.

2. Zur OU „Domain Controllers“ navigieren.

3. Den Eintrag des alten (toten) DC auswählen.

4. Rechtsklick → „Delete“.

5. Warnmeldung bestätigen.

6. Falls der DC wirklich nicht mehr zurückkommt:

   „Delete this Domain Controller anyway“ aktivieren.

   Löschvorgang bestätigen.

## 6. Clean up Sites and Services and DNS

1. Abschließend erneut „Active Directory Sites and Services“ öffnen.

2. Sicherstellen, dass keine weiteren Referenzen auf den alten DC vorhanden sind.

3. Zusätzlich DNS bereinigen:
   
   DNS Manager öffnen.

   Unter den Forward Lookup Zones alle SRV-Records prüfen.

   Veraltete Einträge zum alten DC entfernen.

4. Dies verhindert spätere DNS-Probleme oder Verzögerungen.
   


   
