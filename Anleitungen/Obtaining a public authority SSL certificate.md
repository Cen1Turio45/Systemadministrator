# Obtaining a public authority SSL certificate

<br></br>

## Vorbereitung

1. Ein öffentliches SSL-Zertifikat wird benötigt, um HTTPS auf dem Webserver zu aktivieren.

2. Im Beispiel wird ein Windows Server 2025 Webserver mit IIS 10 verwendet.

<br></br>

## Ziel

1. Ein SSL-Zertifikat einer öffentlichen Zertifizierungsstelle (Public CA) beziehen.

2. Der Prozess besteht aus drei Schritten:

   Certificate Request (CSR) erstellen

   CSR bei der Public CA einreichen

   Zertifikat auf dem Server installieren

