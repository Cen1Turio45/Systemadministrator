# Creating an auto-enrollment policy

<br></br>

## Ziel der Auto-Enrollment Policy

1. Der CA-Server ist eingerichtet und kann Zertifikate ausstellen.

2. Viele Computer im Netzwerk benötigen jedoch automatisch ein Zertifikat.

3. Mit Auto-Enrollment wird die Zertifikatverteilung automatisiert – keine manuelle Zertifikatsanforderung pro Gerät.

4. Zusätzlich erneuert Auto-Enrollment Zertifikate automatisch, bevor sie ablaufen.

5. Dadurch entfällt der regelmäßige administrative Aufwand für Zertifikatserneuerungen.

<br></br>

## Prüfung der ausgestellten Zertifikate

1. Auf dem CA-Server die Certification Authority öffnen.

2. Unter Issued Certificates überprüfen, wie viele Zertifikate bisher ausgestellt wurden.

3. Diese Ansicht dient später als Kontrolle, ob die Auto-Enrollment Policy funktioniert.

<br></br>

## GPO für Auto-Enrollment erstellen

1. Auf einem Domain Controller Group Policy Management öffnen.

2. Ein neues GPO erstellen, z. B. „Enable Certificate Auto-Enrollment“.

3. Mit Rechtsklick → Edit das GPO bearbeiten.

<br></br>

## Einstellungen der Auto-Enrollment Policy konfigurieren

Navigieren zu:

Computer Configuration | Policies | Windows Settings | Public Key Policies  Certificatr Services Client | Auto-Enrollment

1. Einstellung öffnen und auf Enabled setzen.

2. Aktivieren der Optionen:

   „Renew expired certificates, update pending certificates, and remove revoked certificates“

   „Update certificates that use certificate templates“

3. Optional: Ablaufwarnungen aktivieren (z. B. 10 %).

<br></br>

## GPO verlinken und aktivieren

1. Das GPO muss mit der gewünschten OU oder der gesamten Domain verknüpft werden.

2. Für Testumgebungen kann das GPO auf Domain-Ebene verlinkt werden.

3. GPO replizieren lassen und sicherstellen, dass es auf alle Clients angewendet wird.

<br></br>

## Auto-Enrollment Permissions im Template aktivieren

1. Auf dem CA-Server Certificate Templates öffnen.

2. Die entsprechende Zertifikatvorlage per Rechtsklick → Properties öffnen.

3. Zum Tab Security wechseln.

4. Der Gruppe Domain Computers die Berechtigung Autoenroll geben.

5. Nur so kann das Template automatisch an Computer verteilt werden.

<br></br>

## Funktion überprüfen

1. Einige Minuten warten, bis Active Directory und GPO repliziert wurden.

2. Zurück zum CA-Server und unter Issued Certificates nachsehen.

3. Nun sollten deutlich mehr Zertifikate angezeigt werden – die neuen Zertifikate wurden automatisch verteilt.

<br></br>

## Zusammenfassung der Funktionsweise

1. Sobald ein Template veröffentlicht wurde und Auto-Enrollment im GPO aktiv ist, fordert jeder Domain-Computer automatisch Zertifikate an – basierend auf den Berechtigungen im Template.

2. Wenn das Zertifikat kurz vor dem Ablauf steht, erneuert die Policy es selbstständig.

3. Dies automatisiert den gesamten Zertifikatslebenszyklus und reduziert den administrativen Aufwand erheblich.

<br></br>
