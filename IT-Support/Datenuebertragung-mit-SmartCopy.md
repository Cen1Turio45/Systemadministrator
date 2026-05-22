# Datenübertragung mit SmartCopy

## Ziel

Diese Anleitung beschreibt eine strukturierte Datenübertragung von einem alten Datenträger auf einen neuen Datenträger mit SmartCopy.

## Vorbereitung

Vor der Übertragung prüfen:

- Welcher Datenträger ist die Quelle?
- Welcher Datenträger ist das Ziel?
- Ist im neuen Gerät eine NVMe oder SATA-SSD verbaut?
- Kann das Zielsystem nach der Übertragung von dem neuen Datenträger starten?
- Sind wichtige Daten zusätzlich gesichert?

Wenn ein System von SATA auf NVMe umgestellt wird, sollte vorher geprüft werden, ob Windows die benötigten NVMe-Treiber bereits kennt. In manchen Fällen ist es sinnvoll, die NVMe vorher im alten System einzubauen, damit Windows passende Treiber laden kann.

## Durchführung

1. Original-SSD als Quelle einbauen.
2. Ziel-SSD per USB anschließen.
3. Quelle und Ziel eindeutig identifizieren.
4. Vor dem Start erneut prüfen, dass Quelle und Ziel nicht vertauscht sind.
5. In SmartCopy geeignete Optionen setzen:

- kopierte Daten verifizieren
- falls möglich Ziellaufwerk zu GPT konvertieren

6. Datenübertragung starten.
7. Übertragung vollständig durchlaufen lassen.

## Nachkontrolle

Nach der Übertragung:

1. System mit dem neuen Datenträger starten.
2. Geräte-Manager öffnen.
3. Treiber prüfen.
4. Fehlende oder fehlerhafte Treiber aktualisieren.
5. Windows-Start, Anmeldung und wichtige Anwendungen testen.

## Wichtige Hinweise

- Quelle und Ziel immer doppelt prüfen.
- Vor produktiver Übergabe einen Neustart testen.
- Bei Treiberproblemen nicht blind Treiber-Tools verwenden, sondern Herstellerquellen bevorzugen.
- Vor der Übergabe prüfen, ob Benutzerdateien, Programmeinstellungen und wichtige Anwendungen vorhanden sind.

## Dokumentation im Ticket

Festhalten:

- Quellgerät
- Zielgerät
- verwendete Datenträger
- Ergebnis der Verifikation
- Starttest erfolgreich: ja/nein
- Treiberprüfung durchgeführt: ja/nein
