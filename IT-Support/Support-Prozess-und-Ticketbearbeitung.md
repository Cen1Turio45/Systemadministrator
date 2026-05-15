# Support-Prozess und Ticketbearbeitung

## Ziel

Diese Anleitung beschreibt, wie ein Supportfall strukturiert aufgenommen, analysiert, dokumentiert und bei Bedarf eskaliert wird.

## Grundprinzip

Ein guter Supportprozess beantwortet drei Fragen:

- Was ist das Problem?
- Wer oder was ist betroffen?
- Was wurde bereits geprüft und was ist der nächste Schritt?

## Standardvorgehen

1. Problem aufnehmen und Umfang klären.
2. Betroffene Benutzer, Geräte, Standorte und Systeme erfassen.
3. Physische Grundlagen prüfen, z. B. Strom, Kabel, Dockingstation, Netzwerk, Drucker oder Monitor.
4. Problem mit Remote-Tools, Monitoring oder Benutzer-Screensharing nachvollziehen.
5. Logs, Fehlermeldungen und Screenshots sichern.
6. Benutzer über Status, nächste Schritte und erwartete Dauer informieren.
7. Lösung dokumentieren oder Ticket sauber eskalieren.

## Gute Troubleshooting-Notizen

Eine Ticketnotiz sollte kurz, aber vollständig sein.

```text
Problem:
Benutzer kann sich seit 08:30 Uhr nicht mit dem WLAN verbinden.

Betroffen:
Ein Benutzer, Gerät WIN11-042, Standort Büro 2.

Geprüft:
- WLAN bei anderem Benutzer funktioniert.
- Gerät neu gestartet.
- IP-Konfiguration geprüft.
- Netzwerkadapter aktiv.
- Ereignisanzeige ohne klaren Treiberfehler.

Ergebnis:
Problem besteht weiterhin.

Nächster Schritt:
Treiberprüfung und ggf. Eskalation an Netzwerkteam.
```

## Priorisierung

| Priorität | Beschreibung | Beispiel |
| --- | --- | --- |
| Critical | Geschäftsbetrieb oder Sicherheit stark betroffen | Standort ohne Internet, Malware-Ausbruch |
| High | Mehrere Benutzer oder kritische Systeme betroffen | Abteilung kann nicht drucken, M365-Störung |
| Medium | Einzelner Benutzer oder nicht kritisches System | Einzelner Client hat Softwareproblem |
| Low | Kleine Einschränkung oder Informationsanfrage | Darstellungsproblem, How-to-Frage |

## Eskalation

Ein Ticket sollte eskaliert werden, wenn:

- das Problem außerhalb der eigenen Berechtigung liegt
- ein kritisches System betroffen ist
- mehrere Benutzer betroffen sind
- Logs oder Fehlerbilder Spezialwissen erfordern
- ein Sicherheitsvorfall möglich ist

## Eskalationsnotiz

Eine gute Eskalationsnotiz enthält:

- Zusammenfassung des Problems
- betroffene Benutzer, Geräte und Systeme
- bisherige Schritte und Ergebnis je Schritt
- Fehlermeldungen, Logs oder Screenshots
- Einschätzung der Dringlichkeit
- empfohlener nächster Schritt

```text
Eskalation an Netzwerkteam:
Seit 09:15 Uhr können alle Benutzer am Standort Singen keine externen Webseiten erreichen.
Interne Freigaben sind erreichbar. M365 und externe Webseiten sind nicht erreichbar.
Router wurde noch nicht neu gestartet, da Freigabe durch Standortleitung fehlt.
Bitte WAN-Verbindung, Firewall und Providerstatus prüfen.
```

## Benutzerkommunikation

Benutzer sollten wissen:

- dass das Problem aufgenommen wurde
- was aktuell geprüft wird
- ob sie etwas tun müssen
- wann sie ein Update erwarten können

Eine ruhige, klare Kommunikation reduziert Rückfragen und zeigt Professionalität.
