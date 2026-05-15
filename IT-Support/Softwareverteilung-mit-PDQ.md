# Softwareverteilung mit PDQ

## Ziel

Diese Anleitung beschreibt ein sauberes Vorgehen zur Softwareverteilung mit PDQ Deploy in einer Windows-Umgebung.

## Grundidee

Software sollte nicht direkt ungeprüft auf alle Clients verteilt werden. Besser ist ein kontrollierter Ablauf:

1. Installationsdatei vorbereiten.
2. Silent-Installation recherchieren.
3. Paket in PDQ erstellen.
4. Auf Testgerät ausrollen.
5. Ergebnis prüfen.
6. Erst danach breiter ausrollen.

## Vorbereitung

1. Installationsdatei von offizieller Herstellerseite herunterladen.
2. Datei in einem administrativen Software-Share ablegen.
3. Prüfen, ob es eine MSI-Datei gibt.
4. Silent-Parameter recherchieren.

Beispiele:

```cmd
setup.exe /S
msiexec /i package.msi /qn
```

Die Parameter unterscheiden sich je nach Hersteller und müssen vor dem Deployment geprüft werden.

## Paket erstellen

1. PDQ Deploy öffnen.
2. `New Package` auswählen.
3. Paket sinnvoll benennen.
4. Neuen Installationsschritt hinzufügen.
5. Installationsdatei aus dem Software-Share auswählen.
6. Silent-Parameter setzen.
7. Paket speichern.

## Testdeployment

1. Ein einzelnes Testgerät auswählen.
2. Prüfen, ob das Gerät erreichbar ist:

```cmd
ping CLIENTNAME
```

3. Paket auf dem Testgerät deployen.
4. Installation prüfen.
5. Anwendung starten und Funktion testen.
6. Einen Tag beobachten, falls es sich um produktiv wichtige Software handelt.

## Häufige Fehlerquellen

| Fehler | Prüfung |
| --- | --- |
| Gerät nicht erreichbar | DNS, Firewall, Netzwerk, Ping |
| Zugriff verweigert | Deployment-Account und Berechtigungen prüfen |
| Installation hängt | Silent-Parameter prüfen |
| Falsche Version installiert | Paketquelle und Dateiname prüfen |
| Reboot erforderlich | Neustartverhalten im Paket definieren |

## Rollout

Nach erfolgreichem Test kann das Paket auf eine Gruppe oder OU ausgerollt werden. Der Rollout sollte in Wellen erfolgen, damit Fehler früh auffallen und nicht sofort alle Clients betroffen sind.

## Dokumentation

Im Ticket oder Deployment-Log sollten festgehalten werden:

- Paketname und Version
- Zielgeräte oder Zielgruppe
- Testgerät
- Zeitpunkt des Rollouts
- Ergebnis
- bekannte Auffälligkeiten
