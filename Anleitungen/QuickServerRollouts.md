# Quick Server Rollouts mit Sysprep

<br></br>

## 1. Installation des Windows Server 2025 auf dem Master-Server

1. Windows Server 2025 regulär installieren.

2. Keine Rollen oder Features installieren, die Gerätekonfigurationen an einen bestimmten Host binden könnten.

3. Alle notwendigen Gerätetreiber installieren und sicherstellen, dass das System vollständig funktionsfähig ist.

4. Der Server dient als Grundlage für das spätere Master-Image.

<br></br>

## 2. Konfigurationen und Updates auf dem Master-Server durchführen

1. Alle gewünschten Systemeinstellungen vornehmen, die später auf allen Servern identisch sein sollen.

2. Dateien, Tools oder Ordner integrieren, die auf jedem künftigen Server verfügbar sein sollen.

3. Dienste nach Bedarf aktivieren oder deaktivieren.

4. Registry-Einstellungen anpassen, sofern Teil des Hardening-Prozesses.

5. Windows-Updates installieren und das System vollständig patchen.

6. Optional: Nach Abschluss aller Anpassungen Tests durchführen, um sicherzustellen, dass das System fehlerfrei funktioniert.

<br></br>

## 3. Sysprep vorbereiten und ausführen

<br></br>

### 3.1 Wichtige Sysprep-Parameter

/generalize: Entfernt eindeutige Systeminformationen (z. B. SID), damit neue Server individuelle Identitäten erhalten.

/oobe: Aktiviert den Windows-Ersteinrichtungsprozess beim ersten Start des neuen Systems.

/shutdown: Fährt das System nach Abschluss herunter und verhindert einen Neustart.

<br></br>

### 3.2 Sysprep-Befehl

Folgender Befehl wird in einer administrativen Eingabeaufforderung ausgeführt:

sysprep.exe /generalize /oobe /shutdown

Nach Ausführung fährt der Server vollständig herunter und darf nicht erneut gestartet werden, bevor das Image erstellt wurde.

<br></br>

## 4. Master-Image des Servers erstellen

1. Der Server ist nun heruntergefahren und bereit zur Image-Erstellung.

2. Physische Server: Eine Imaging-Software verwenden (z. B. Acronis), um ein vollständiges Abbild der Systemfestplatte zu erzeugen.

3. Virtuelle Server (Hyper-V):

Die VHDX-Datei des Servers kopieren.

Die Datei sinnvoll benennen, z. B. „WS2025_Master_withUpdates.vhdx“.

4. Das Master-Image an einem zentralen, sicheren Speicherort ablegen.

5. Das Master-Image selbst darf nicht gebootet werden, da dies die Sysprep-Vorbereitung entfernen würde.

6. Neue Server werden ausschließlich durch Kopien dieses Images erstellt.

## 5. Neue Server aus dem Master-Image bereitstellen

1. Für jeden neuen Server eine Kopie des Master-Images erstellen.

2. Die kopierte Image-Datei ablegen und bei Bedarf entsprechend der Serverrolle umbenennen.

3. Den neuen Server aus der kopierten Image-Datei starten.

4. Beim ersten Start erfolgt:

Der Windows-OOBE-Setup-Assistent

Eine automatische Generierung einer neuen SID

Zuweisung eines zufälligen Hostnamens

5. Den Server nach dem Setup in den gewünschten Hostnamen umbenennen.

6. Weitere Konfigurationen (Domänenbeitritt, Rollen, Anwendungen) wie üblich durchführen.
