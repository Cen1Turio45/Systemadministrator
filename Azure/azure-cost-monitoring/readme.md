# Azure Cost Monitoring mit Azure Functions

## Ziel

Azure-Kosten sichtbar machen, Budgets setzen und automatisch einen Kostenbericht per E-Mail versenden.

## Umgesetzt

- Budgets und Warnungen in Azure Cost Management erstellt.
- Kosten nach Services und Ressourcengruppen ausgewertet.
- Azure Function für wiederkehrenden Kostenbericht aufgebaut.
- Managed Identity für sicheren Zugriff auf Azure-Daten genutzt.
- Azure Communication Services für den E-Mail-Versand angebunden.
- Kostenbericht als HTML- und Text-Mail erzeugt.

## Projektdateien

- [src/functions/Time_Trigger.js](src/functions/Time_Trigger.js): Timer Function, Kostenabfrage, Reportaufbau und E-Mail-Versand
- [Codereview.md](Codereview.md): kurze Code- und Architekturprüfung
- [package.json](package.json): Node.js-Abhängigkeiten und Testskripte
- [host.json](host.json): Azure Functions Host-Konfiguration
- `local.settings.json`: lokale Settings, nicht für GitHub gedacht

## Wichtige Azure-Dienste

- Azure Cost Management
- Azure Budgets
- Azure Functions
- Managed Identity
- Azure Communication Services
- Email Communication Services
- App Settings / Umgebungsvariablen

## Worauf man achten muss

- Budgetwarnungen sauber eingrenzen: Subscription, Ressourcengruppe, Service oder Tags.
- Function App mit passender Identität ausstatten.
- Rolle `Kostenverwaltungsleser` vergeben, sonst kann die Function keine Kostendaten lesen.
- Communication Services und Email Communication Services korrekt miteinander verbinden.
- Absenderadresse muss zur verifizierten Domain passen.
- App Settings exakt setzen, besonders `AZURE_SUBSCRIPTION_ID`, `ACS_EMAIL_FROM` und Connection Strings.
- Nicht mehrere ähnliche Azure-Ressourcen parallel liegen lassen, sonst wird die Zuordnung schnell unübersichtlich.

## Typische Fehler

- `DomainNotLinked`: Email-Domain ist nicht mit der Communication-Services-Ressource verbunden.
- `InvalidSenderUserName`: Absenderadresse passt nicht zur verifizierten Domain.
- `Denied`: Berechtigung, Sender oder Ressourcenzuordnung passt nicht.
- Keine Kostendaten: Managed Identity oder Rolle fehlt.
- Function läuft nicht: App Settings, Runtime oder Deployment prüfen.

## Gelernt

- Cloud-Probleme liegen oft nicht im Code, sondern in Berechtigungen, Verknüpfungen und App Settings.
- Kostenmonitoring ist nur hilfreich, wenn Budgets, Berichte und Zuständigkeiten klar sind.
- Wenige sauber benannte Ressourcen sind besser als viele Testressourcen ohne klare Zuordnung.

## Screenshots

Azure Kostenanalyse

<img width="1886" height="891" alt="Azure Kostenanalyse" src="https://github.com/user-attachments/assets/b9144d8c-b402-41cd-89ff-b9459a9f9456" />

Budgetwarnung

<img width="1430" height="804" alt="Budgetwarnung" src="https://github.com/user-attachments/assets/9d761bfd-e9e2-49af-8cb1-722fd23de376" />

Function App

<img width="1910" height="632" alt="Function App" src="https://github.com/user-attachments/assets/14fb0fe9-b302-46b4-8fd1-5aa971909ab1" />

Erfolgreiche Logs

<img width="1691" height="318" alt="Erfolgreiche Logs" src="https://github.com/user-attachments/assets/9d2df610-492c-4471-82b1-8d7c7893402e" />

Empfangene E-Mail

<img width="1078" height="764" alt="Empfangene E-Mail" src="https://github.com/user-attachments/assets/4012d666-9b89-4c9f-a8cb-5019928e84c5" />
