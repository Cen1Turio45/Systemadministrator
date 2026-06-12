# Gruppenrichtlinien prüfen mit gpresult

## Ziel

Kurze Checkliste zum Prüfen angewendeter Gruppenrichtlinien.

## Checkliste

- Betroffenen Benutzer, Computer und erwartete Einstellung klären.
- In `Group Policy Management` relevante OU und verknüpfte GPOs prüfen.
- Sicherheitsfilterung und WMI-Filter prüfen.
- Auf dem Client administratives Terminal öffnen.
- HTML-Bericht mit `gpresult /h C:\gpresult.html` erstellen.
- Bericht öffnen und angewendete Benutzer- und Computer-GPOs prüfen.
- Abgelehnte oder gefilterte GPOs beachten.
- Bei Bedarf `gpupdate /force` ausführen.
- Danach abmelden, neu anmelden oder Gerät neu starten, wenn die Policy es erfordert.

## Nützliche Befehle

```cmd
gpresult /h C:\gpresult.html
gpupdate /force
```
