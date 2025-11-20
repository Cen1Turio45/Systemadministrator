# Bootable USB-Stick with PowerShell erstellen

<br></br>

## 1. ISO-Datei einbinden:
ISO-Datei herunterladen und über Rechtsklick Bereistellen auswählen.

Laufwerksbuchstaben des eingebundenen ISO-Laufwerks notieren.

<br></br>

## 2. USB-Stick anschließen:
USB-Stick einstecken und den zugewiesenen Laufwerksbuchstaben notieren.

<br></br>

## 3. PowerShell starten und USB-Laufwerk auswählen:
$usbDriveLetter = Read-Host "Enter USB drive letter (Ex: E)"

<br></br>

## 4. USB-Stick formatieren:
Format-Volume -DriveLetter $usbDriveLetter -FileSystem NTFS -NewFileSystemLabel "WinServerUSB" -Confirm:$false | Out-Null

<br></br>

