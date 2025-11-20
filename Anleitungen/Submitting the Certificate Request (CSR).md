# Public CA Website aufrufen

<br></br>

## Public CA Website aufrufen

1. Auf der Website der gewählten Public CA anmelden (z. B. GoDaddy, DigiCert, Verisign).

2. Bereich für SSL-Zertifikate und Certificate Request / Create Certificate öffnen.

<br></br>

## Erforderliche Angaben bereitstellen

<img width="719" height="421" alt="image" src="https://github.com/user-attachments/assets/020f4f37-5d59-47fe-8a30-5b503348188b" />

1. Validity Period

   Zertifikatslaufzeit auswählen (meist 1 Jahr).

2. Webserver Platform

   IIS auswählen (bei Windows Server 2025).

   Alternativen könnten Apache, Tomcat, NGINX, etc. sein.

3. Domain Ownership Validation

   E-Mail-Adresse zur Validierung auswählen.

   Typische Optionen:

   admin@contoso.com

   administrator@contoso.com

   webmaster@contoso.com

   hostmaster@contoso.com

4. Validierungs-E-Mail öffnen → Link anklicken oder Code eingeben.

<br></br>

## CSR

1. Formular absenden.

2. CA verarbeitet den CSR und stellt das SSL-Zertifikat bereit.
