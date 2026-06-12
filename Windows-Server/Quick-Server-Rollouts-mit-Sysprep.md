# Quick Server Rollouts mit Sysprep

## Ziel

Kurze Checkliste zum Erstellen eines wiederverwendbaren Windows-Server-Master-Images.

## Checkliste

- Windows Server regulär auf dem Master-System installieren.
- Keine rollen- oder hostgebundenen Einstellungen einbauen, die später Probleme machen.
- Benötigte Treiber, Tools, Ordner und Basiseinstellungen vorbereiten.
- Windows Updates vollständig installieren.
- System vor Sysprep testen.
- Administrative Eingabeaufforderung öffnen.
- Sysprep mit `/generalize /oobe /shutdown` ausführen.
- Nach Sysprep das Master-System nicht mehr starten.
- Image oder VHDX im ausgeschalteten Zustand sichern.
- Neue Server nur aus Kopien des Master-Images erstellen.
- Neuen Server starten, OOBE abschließen und Hostname setzen.
- Danach Domänenbeitritt, Rollen und Anwendungen konfigurieren.

## Befehl

```cmd
sysprep.exe /generalize /oobe /shutdown
```
