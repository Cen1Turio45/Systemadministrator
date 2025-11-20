# Publishing the template

<br></br>

## Vorbedingungen

1. Die bearbeitete Zertifikatvorlage wurde erstellt und gespeichert.

2. Die Template-Management-Konsole kann nun geschlossen werden, sodass man wieder in der Hauptansicht der Certification Authority ist.

<br></br>

## Zertifikatvorlage veröffentlichen

<img width="744" height="339" alt="image" src="https://github.com/user-attachments/assets/41e4f7f7-c190-4e3e-b3ed-573e13aa5dfc" />

1. In der Certification Authority die CA auswählen.

2. Den Ordner Certificate Templates mit Rechtsklick öffnen.

3. New auswählen und anschließend Certificate Template to Issue anklicken.

4. Eine Liste aller verfügbaren, aber noch nicht aktivierten Zertifikatvorlagen erscheint.

5. Die neu erstellte Vorlage aus der Liste auswählen.

6. Mit OK bestätigen, um die Vorlage zu veröffentlichen.

7. Die Vorlage wird nun in die Liste der „Issued Certificate Templates“ aufgenommen und kann von Clients angefordert werden.

<br></br>

## Falls die neue Vorlage nicht sichtbar ist

<img width="697" height="300" alt="image" src="https://github.com/user-attachments/assets/7aa8cd03-63dd-42b5-8c9e-6754741f6a65" />

1. Replikation abwarten

   In manchen Fällen dauert es, bis die Änderungen an alle Domain Controller repliziert wurden.
   Kurz warten und anschließend erneut versuchen.

2. CA-Dienst neu starten

   In der Certification Authority-Konsole den CA-Namen rechtsklicken.
   All Tasks → Stop Service auswählen.
   Nach ein bis zwei Sekunden erneut den CA-Namen rechtsklicken.
   All Tasks → Start Service auswählen.
   Danach erneut versuchen, die neue Vorlage unter
   Certificate Templates → New → Certificate Template to Issue zu veröffentlichen.
   Die Vorlage sollte nun in der Liste erscheinen.
