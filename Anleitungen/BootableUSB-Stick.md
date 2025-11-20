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

## ISO-Laufwerk auswählen:
$isoMountPointDriveLetter = Read-Host "Enter ISO mount point drive letter (Ex: F)"

<br></br>

## Dateien vom ISO auf den USB-Stick kopieren:
$source = "$($isoMountPointDriveLetter):"
$destination = "$($usbDriveLetter):"
robocopy $source $destination /COPYALL /Z /E /SEC /R:3 /W:3

<br></br>

## USB-Stick bootfähig machen:
usbDriveNumber = (Get-WmiObject -Class Win32_DiskDrive |

Where-Object {$_.InterfaceType -eq "USB" -and $_.DeviceID -like "*$usbDriveLetter"}).Index |

bootsect /nt60 $usbDriveLetter | Out-Null

<br></br>

## Abschlussmeldung:
Write-Host "Copy operation complete" 
Start-Sleep -Seconds 2

<br></br>
