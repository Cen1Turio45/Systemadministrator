# Creating a Certificate Signing Request (CSR)

<br></br>

## IIS öffnen und Zertifikatsverwaltung aufrufen

1. IIS über Server Manager → Tools → Internet Information Services (IIS) Manager öffnen.

2. In der linken Navigation den Webserver auswählen (z. B. WEB1).

3. In der mittleren Ansicht Server Certificates doppelklicken.

<br></br>

## CSR-Assistent starten

1. Auf der rechten Seite im Bereich Actions auf Create Certificate Request… klicken.

<br></br>

## Distinguished Name Properties ausfüllen

1. Die folgenden Felder ausfüllen:

   Common name: DNS-Name der Website (z. B. portal.contoso.com)

   Organization: Firmenname

   Organizational unit: Abteilung (frei wählbar, z. B. Web)

   City/locality: Ort ausschreiben

   State/province: Bundesland/Staat ausschreiben

   Country/region: Ländercode (z. B. US, DE, CH)

<br></br>

## Kryptografie-Einstellungen setzen

1. Cryptographic service provider: Standardwert beibehalten (Microsoft RSA SChannel Cryptographic Provider).

2. Bit length: auf 2048 oder höher setzen (empfohlener Mindestwert).

<br></br>

## CSR-Datei speichern

1. Einen Dateinamen und Speicherort auswählen.

2. CSR wird als .txt oder .req gespeichert und enthält den öffentlichen Schlüssel.

3. Die Datei wird später bei der Public CA eingereicht.

<br></br>
   
