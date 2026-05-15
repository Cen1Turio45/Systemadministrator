# Creating a Certificate Signing Request (CSR)

<br></br>

## IIS öffnen und Zertifikatsverwaltung aufrufen

<img width="854" height="454" alt="image" src="https://github.com/user-attachments/assets/9b962e7a-43a4-4c66-a043-ce659ab236c2" />

1. IIS über Server Manager → Tools → Internet Information Services (IIS) Manager öffnen.

2. In der linken Navigation den Webserver auswählen (z. B. WEB1).

3. In der mittleren Ansicht Server Certificates doppelklicken.

<br></br>

## CSR-Assistent starten

1. Auf der rechten Seite im Bereich Actions auf Create Certificate Request… klicken.

<br></br>

## Distinguished Name Properties ausfüllen

<img width="761" height="401" alt="image" src="https://github.com/user-attachments/assets/5a362036-8327-4800-aa09-d981a59b6731" />

1. Die folgenden Felder ausfüllen:

   Common name: DNS-Name der Website (z. B. portal.contoso.com)

   Organization: Firmenname

   Organizational unit: Abteilung (frei wählbar, z. B. Web)

   City/locality: Ort ausschreiben

   State/province: Bundesland/Staat ausschreiben

   Country/region: Ländercode (z. B. US, DE, CH)

<br></br>

## Kryptografie-Einstellungen setzen

<img width="409" height="151" alt="image" src="https://github.com/user-attachments/assets/8c68fbf4-07f1-405c-b84e-918918d88528" />

1. Cryptographic service provider: Standardwert beibehalten (Microsoft RSA SChannel Cryptographic Provider).

2. Bit length: auf 2048 oder höher setzen (empfohlener Mindestwert).

<br></br>

## CSR-Datei speichern

1. Einen Dateinamen und Speicherort auswählen.

2. CSR wird als .txt oder .req gespeichert und enthält den öffentlichen Schlüssel.

3. Die Datei wird später bei der Public CA eingereicht.

<br></br>
   
