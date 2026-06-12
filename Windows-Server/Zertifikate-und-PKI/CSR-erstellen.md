# CSR erstellen

## Ziel

Kurze Checkliste zum Erstellen eines Certificate Signing Requests in IIS.

## Checkliste

- IIS Manager öffnen.
- Webserver auswählen.
- `Server Certificates` öffnen.
- `Create Certificate Request` starten.
- Common Name mit dem DNS-Namen der Website eintragen.
- Organisation, Abteilung, Ort, Bundesland und Ländercode eintragen.
- Kryptografieanbieter auf Standardwert lassen, wenn keine Vorgabe abweicht.
- Bitlänge auf mindestens `2048` setzen.
- CSR-Datei speichern.
- CSR-Datei bei der Public CA einreichen.
