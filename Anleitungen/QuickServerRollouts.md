# Quick Server Rollouts mit Sysprep

<br></br>

## 1. Installation des Windows Server 2025 auf dem Master-Server

Windows Server 2025 regulär installieren.

Keine Rollen oder Features installieren, die Gerätekonfigurationen an einen bestimmten Host binden könnten.

Alle notwendigen Gerätetreiber installieren und sicherstellen, dass das System vollständig funktionsfähig ist.

Der Server dient als Grundlage für das spätere Master-Image.

<br></br>

## 2. Konfigurationen und Updates auf dem Master-Server durchführen

Alle gewünschten Systemeinstellungen vornehmen, die später auf allen Servern identisch sein sollen.

Dateien, Tools oder Ordner integrieren, die auf jedem künftigen Server verfügbar sein sollen.

Dienste nach Bedarf aktivieren oder deaktivieren.

Registry-Einstellungen anpassen, sofern Teil des Hardening-Prozesses.

Windows-Updates installieren und das System vollständig patchen.

Optional: Nach Abschluss aller Anpassungen Tests durchführen, um sicherzustellen, dass das System fehlerfrei funktioniert.

<br></br>
