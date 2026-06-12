# Bootfähigen USB-Stick mit PowerShell erstellen

## Ziel

Kurze Checkliste zum Erstellen eines Windows-Installationssticks.

## Checkliste

- Windows-ISO bereithalten.
- USB-Stick anschließen und Laufwerksbuchstaben prüfen.
- PowerShell als Administrator starten.
- ISO per Rechtsklick > `Bereitstellen` einbinden.
- Laufwerksbuchstaben von ISO und USB-Stick notieren.
- Vor dem Formatieren sicher prüfen, dass wirklich der USB-Stick ausgewählt ist.
- USB-Stick mit NTFS formatieren.
- Dateien mit `robocopy` von der ISO auf den USB-Stick kopieren.
- USB-Stick mit `bootsect /nt60` bootfähig machen.
- Stick an einem Testgerät im Bootmenü prüfen.
