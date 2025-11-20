# Templates Certificate

<br></br>

## Creating a Certificate Template

1. Ein Certificate Authority (CA) Server stellt Zertifikate aus.

2. Zertifikate basieren nicht direkt auf freien Einstellungen, sondern immer auf Zertifikatvorlagen (Templates).

3. Diese Templates definieren alle Eigenschaften, die später im Zertifikat enthalten sind.

4. Neue Zertifikate werden generiert, indem der CA-Server die ausgewählte Vorlage „nach Rezept“ nutzt.

5. Obwohl Windows einige Standardvorlagen bereitstellt, ist es empfehlenswert, eigene Templates zu erstellen, um volle Kontrolle über alle Konfigurationen zu haben.

<br></br>

## Zertifikatvorlagen-Konsole öffnen

1. Server Manager öffnen.

2. „Tools“ auswählen.

3. „Certification Authority“ öffnen.

4. In der linken Struktur die CA auswählen.

5. Den Ordner Certificate Templates per Rechtsklick öffnen.

6. „Manage“ auswählen, um die vollständige Template-Konsole zu öffnen.

<br></br>

## Basisvorlage auswählen und duplizieren

1. In der Template-Konsole wird eine erweiterte Liste aller verfügbaren Vorlagen angezeigt.

2. Eine geeignete Vorlage aussuchen, die dem gewünschten Anwendungsfall ähnelt
(z. B. „Computer“ für Maschinenzertifikate).

3. Rechtsklick auf die ausgewählte Standardvorlage.

4. „Duplicate Template“ auswählen, um eine neue Vorlage darauf basierend zu erstellen.

<br></br>

## Allgemeine Eigenschaften anpassen

1. Die neue Vorlage öffnet sich im Eigenschaftenfenster.

2. Einen eindeutigen Vorlagennamen vergeben.

3. Einen passenden Anzeigenamen (Display Name) festlegen.

4. Die gewünschte Gültigkeitsdauer einstellen (Beispiel aus dem Screenshot: 2 Jahre).

5. Die Erneuerungsfrist konfigurieren (Beispiel: 6 Wochen).

6. Optional: „Publish certificate in Active Directory“ aktivieren.

<br></br>

## Subject Name konfigurieren

1. Tab Subject Name öffnen.

2. Einstellung „Build from this Active Directory Information“ auswählen.

3. „Common name“ als Format festlegen.

4. Sicherstellen, dass DNS Name aktiviert ist.

5. Optionale zusätzliche Attribute (E-Mail, UPN, SPN) nach Bedarf aktivieren oder deaktivieren.

<br></br>

## Sicherheitseinstellungen definieren

1. Tab Security öffnen.

2. Berechtigungen so konfigurieren, dass nur die gewünschten Gruppen Zertifikate anfordern können.

3. Für das Beispiel:
   Gruppe Domain Computers auswählen.

   Berechtigungen:
   Read: aktiviert
   Enroll: aktiviert
   (optional) Autoenroll je nach Anforderung

4. Ziel: Nur autorisierte Computer sollen Zertifikate auf Basis dieser Vorlage anfordern können.

<br></br>

## Vorlage speichern

1. Alle Einstellungen noch einmal prüfen.

2. Mit „OK“ bestätigen.

3. Die neue Vorlage erscheint nun in der Liste der verfügbaren Templates auf dem CA-Server.

4. Diese Vorlage steht ab sofort für zukünftige Zertifikatsanforderungen zur Verfügung.
