# Bootfähigen USB-Stick mit PowerShell erstellen

## Ziel

Ein Windows-Server-Installationsmedium soll per PowerShell auf einen USB-Stick kopiert werden.

## Voraussetzungen

- Windows-ISO ist vorhanden
- USB-Stick ist angeschlossen
- PowerShell wird als Administrator gestartet
- Laufwerksbuchstaben von ISO und USB-Stick sind bekannt

## 1. ISO-Datei einbinden

1. ISO-Datei herunterladen.
2. Rechtsklick auf die ISO-Datei.
3. `Bereitstellen` auswählen.
4. Laufwerksbuchstaben des eingebundenen ISO-Laufwerks notieren.

## 2. USB-Stick auswählen

```powershell
$usbDriveLetter = Read-Host "Enter USB drive letter (Ex: E)"
```

## 3. USB-Stick formatieren

```powershell
Format-Volume `
  -DriveLetter $usbDriveLetter `
  -FileSystem NTFS `
  -NewFileSystemLabel "WinServerUSB" `
  -Confirm:$false | Out-Null
```

## 4. ISO-Laufwerk auswählen

```powershell
$isoMountPointDriveLetter = Read-Host "Enter ISO mount point drive letter (Ex: F)"
```

## 5. Dateien kopieren

```powershell
$source = "$($isoMountPointDriveLetter):"
$destination = "$($usbDriveLetter):"

robocopy $source $destination /COPYALL /Z /E /SEC /R:3 /W:3
```

## 6. USB-Stick bootfähig machen

```powershell
bootsect /nt60 "$($usbDriveLetter):" | Out-Null
```

## 7. Abschlussmeldung

```powershell
Write-Host "Copy operation complete"
Start-Sleep -Seconds 2
```

## Hinweis

Vor dem Formatieren immer prüfen, dass wirklich der USB-Stick ausgewählt wurde. Der Formatierungsbefehl löscht die vorhandenen Daten auf dem angegebenen Laufwerk.
