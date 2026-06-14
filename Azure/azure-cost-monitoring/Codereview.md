# Code Review: Azure Cost Monitoring

## Ziel

Kurzer Review der wichtigsten Architektur-, Sicherheits- und Testpunkte im Azure-Cost-Monitoring-Projekt.

## Architektur

- Azure Cost Management liefert Kostendaten.
- Azure Function läuft zeitgesteuert.
- Managed Identity authentifiziert ohne Secrets im Code.
- Rolle `Kostenverwaltungsleser` erlaubt Zugriff auf Cost Management.
- Azure Communication Services verschickt den Report per E-Mail.
- App Settings steuern Subscription, Empfänger, Schwellwerte und Sender.

## Kritische Prüfpunkte

- Managed Identity muss aktiviert und berechtigt sein.
- `AZURE_SUBSCRIPTION_ID` muss zur richtigen Subscription passen.
- `REPORT_RECIPIENTS` und `ACS_EMAIL_FROM` müssen korrekt gesetzt sein.
- Communication Services und Email Domain müssen verbunden sein.
- Pflichtspalten aus der Cost Management API dürfen nicht fehlen.
- Kostenwerte dürfen nicht stillschweigend zu `0` werden.
- Mehrere Währungen im selben Report sollten abgefangen werden.
- Secrets und Connection Strings dürfen nicht geloggt werden.

## Wichtige Testfälle

| Bereich | Erwartung |
| --- | --- |
| gültige API-Antwort | Kostenzeile wird korrekt normalisiert |
| fehlende Pflichtspalte `PreTaxCost` | Function bricht mit Fehler ab |
| ungültiger Kostenwert | Function bricht mit Fehler ab |
| leere Kostenantwort | kein falscher `0 EUR`-Bericht |
| ungültiges Datum | Function bricht mit Fehler ab |
| leere Resource Group | Fallback `Nicht zugeordnet` |
| mehrere Währungen | Report wird nicht erzeugt |

## Sinnvolle Verbesserungen

- Startprüfung für alle Pflicht-App-Settings einbauen.
- API-Antworten strenger validieren.
- Retry mit Backoff für temporäre Azure-API-Fehler ergänzen.
- Unit-Tests für reine Logikfunktionen mit `node:test` ergänzen.
- Infrastructure as Code für Function App, Identity, Rollen und App Settings vorbereiten.

## Fazit

Das Projekt zeigt nicht nur eine Function App, sondern das Zusammenspiel aus Azure-Kostenanalyse, Berechtigungen, App Settings, API-Daten und E-Mail-Versand. Die wichtigsten Risiken liegen bei falscher Konfiguration, unvollständigen API-Daten und zu schwacher Validierung.
