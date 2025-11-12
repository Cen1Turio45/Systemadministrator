# Projektbeschreibung: Foundation – Netzwerkaufbau mit pfSense & Hyper-V
<br></br>

Zielsetzung:
Ziel des Projekts ist der Aufbau einer virtuellen Netzwerkumgebung mit pfSense als zentrale Firewalllösung. Die Umgebung wird vollständig auf Hyper-V realisiert und dient als Grundlage für Tests und die spätere Verwaltung von Netzwerkdiensten.
Das Netzwerk besteht aus drei getrennten Bereichen: einem externen WAN-Netz, einem internen LAN-Netz sowie einer privaten DMZ-Zone. Alle Systeme sollen über die Firewall miteinander kommunizieren können und Zugriff auf das Internet erhalten.

<br></br>

## Netzwerkstruktur:
In Hyper-V werden drei virtuelle Netzwerke eingerichtet:
Ein External Switch für das WAN (IP-Bereich 10.71.31.0/24), ein Internal Switch für das LAN (192.168.0.0/24) sowie ein Private Switch für die DMZ (192.168.1.0/24).
Diese bilden die Basis für die spätere Verbindung der virtuellen Maschinen mit unterschiedlichen Sicherheitszonen.

<br></br>

## Installation und Konfiguration der pfSense-Firewall:
Die pfSense-ISO wird heruntergeladen und bei Bedarf mit 7-ZIP entpackt. Anschließend wird in Hyper-V eine neue virtuelle Maschine erstellt. Dabei ist besonders darauf zu achten, dass der Secure-Boot-Modus deaktiviert wird, da pfSense diesen nicht unterstützt.
Die virtuelle Maschine erhält vier virtuelle Prozessoren und mindestens 4 GB Arbeitsspeicher. Es werden drei virtuelle Netzwerkkarten hinzugefügt – jeweils für WAN, LAN und DMZ.
Nach der Standardinstallation wird die pfSense-Firewall mit folgenden Parametern konfiguriert:

IP-Adresse 10.71.31.210/24, Benutzername „admin“, Passwort „1!demo“.
Das Webinterface wird aktiviert, um die spätere Verwaltung über den Browser zu ermöglichen.

<br></br>

## Erstellung der Testserver:
Für die Überprüfung der Netzwerkverbindungen und Firewall-Regeln werden drei virtuelle Windows Server 2025-Maschinen angelegt:
•	DC01 im WAN-Netz (10.71.31.x) als zukünftiger Domain Controller und Verwaltungsserver.
•	LAN-Server im internen Netz (192.168.0.x) für interne Tests.
•	DMZ-Server im privaten Netz (192.168.1.x) zur Simulation eines abgeschotteten Dienstes.
Ziel ist es, die Kommunikation zwischen allen Netzen sicherzustellen und den Internetzugang über pfSense zu prüfen.

<br></br>

## Konfiguration des DC01:
Der virtuelle Server DC01 wird mit einer 150-GB-Festplatte erstellt und erhält folgende Grundkonfiguration:
Der Computername wird auf DC01 geändert, Remote Desktop aktiviert, die Zeitzone angepasst, eine statische IP-Adresse vergeben und die Internet Explorer-Sicherheitsfunktionen deaktiviert. Anschließend werden alle Windows-Updates installiert.
Nach Abschluss der Grundinstallation wird ein Checkpoint in Hyper-V erstellt, um jederzeit zu einem funktionierenden Zustand zurückkehren zu können.

<br></br>

## Zusätzliche Festplatte und Datenträgerverwaltung:
Für DC01 wird über die Hyper-V-Einstellungen eine zweite virtuelle Festplatte hinzugefügt. Diese wird im Datenträger-Manager initialisiert und formatiert.
Ein häufiger Fehler besteht darin, anstelle einer neuen Festplatte den Speicherort der bestehenden Disk zu verändern, was zur Beschädigung der virtuellen Maschine führen kann.
Deshalb sollte unmittelbar nach der Update-Installation ein Checkpoint angelegt werden, um Systemfehler vermeiden zu können.

<br></br>

## Htsupport-Ordner und Installationsdateien:
Auf dem physischen Hostsystem wird ein USB-Stick mit dem Ordner „htsupport“ eingesteckt. Dieser wird als Netzwerkfreigabe eingerichtet, damit die virtuellen Maschinen darauf zugreifen können.
Die Installationsdateien werden anschließend auf das Laufwerk C der jeweiligen virtuellen Maschine kopiert, in einen neu erstellten Ordner „C:\htsupport“. Von dort aus erfolgt später die Installation der Netman-Software.

<br></br>

## Einrichtung des Domain Controllers und Installation von Netman:
Nach der Vorbereitung wird ein neuer Checkpoint erstellt. Anschließend beginnt die Installation des Domain Controllers.
Aus rechtlichen Gründen darf dieser Teil der Installation nicht dokumentiert werden.
Nach erfolgreicher Einrichtung des Domain Controllers wird erneut ein Checkpoint erstellt, bevor die Installation von Netman durchgeführt wird. Auch dieser Schritt wird aus rechtlichen Gründen nicht detailliert beschrieben.

<br></br>

## Empfehlung und Best Practices:
Nach jedem größeren Arbeitsschritt sollte ein Checkpoint erstellt werden. Vor Änderungen an Netzwerken oder Datenträgern sind grundsätzlich Sicherungskopien anzulegen.
Der Secure-Boot-Modus muss bei der pfSense-VM deaktiviert bleiben.
Das Exportieren und Importieren von virtuellen Maschinen ist ausschließlich in Testumgebungen zulässig und darf in Produktivsystemen nicht angewendet werden, da dies nicht offiziell von Microsoft unterstützt wird.
Firewall-Regeln sollten schrittweise erstellt und anhand von Log-Dateien sowie Ping- und Verbindungstests überprüft werden.

<br></br>

## Ergebnisse:
