# Requesting a certificate from MMC

<br></br>

## MMC vorbereiten und Snap-in hinzufügen

<img width="699" height="386" alt="image" src="https://github.com/user-attachments/assets/76930547-9ea0-4863-a023-341fd22b9d56" />

1. Auf einem Client-Computer MMC öffnen (mmc.exe).

2. Über File → Add/Remove Snap-in das Snap-in Certificates hinzufügen.

3. Beim Hinzufügen auswählen, ob Zertifikate für

   My user account

   Service account

   Computer account

   verwaltet werden sollen.

4. Da das Zertifikat vom Computer verwendet wird, Computer account auswählen.

5. Mit Finish bestätigen.

<br></br> 

## Lokalen Zertifikatspeicher auswählen

1. Auf der nächsten Seite erneut Finish klicken, um die Standardoption Local computer zu übernehmen.

2. Dadurch wird der lokale Computerzertifikatspeicher innerhalb der MMC geladen.

<br></br> 

## Neues Zertifikat vom CA-Server anfordern

<img width="893" height="584" alt="image" src="https://github.com/user-attachments/assets/768625b9-d999-473e-8921-7d8aef6235aa" />

1. Rechtsklick auf Personal.

2. All Tasks → Request New Certificate… auswählen.

3. Der Zertifikatsassistent öffnet sich.

4. Mit Next bestätigen, ohne Einstellungen zu ändern.

5. Den nächsten Bildschirm ebenfalls mit Next bestätigen – der Assistent liest jetzt die verfügbaren CA-Zertifikatvorlagen aus Active Directory.

<br></br> 

## Zertifikatvorlage auswählen

1. Die Liste der verfügbaren Zertifikatvorlagen erscheint.

2. Hier werden nur die Vorlagen angezeigt, deren Berechtigungen dem angemeldeten Computer erlauben, ein Zertifikat zu beziehen.

3. Die zuvor erstellte Vorlage (z. B. DirectAccess Machine) auswählen.

4. Optional: Falls die Vorlage nicht angezeigt wird, Show all templates aktivieren, um sämtliche Vorlagen einzusehen.

5. Die gewünschte Vorlage auswählen und auf Enroll klicken.

<br></br> 

## Zertifikatserstellung und Abschluss

<img width="910" height="532" alt="image" src="https://github.com/user-attachments/assets/6bc06046-031a-4e4b-b467-562afefac1fb" />

1. Der CA-Server verarbeitet die Anfrage und stellt ein neues Zertifikat für den Computer aus.

2. Nach erfolgreicher Ausstellung erscheint das Zertifikat im Speicher: Personal → Certificates.

3. Durch Doppelklick auf das Zertifikat können alle Eigenschaften geprüft werden, inklusive:

   Subject

   Key usage

   Enhanced Key Usage

   Template Information

   Zertifikatpfad

4. Damit ist das Zertifikat erfolgreich installiert und einsatzbereit.
   
   
