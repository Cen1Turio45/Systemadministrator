# Erstes LAB

<img src="images/Lab.png" alt="Lab Screenshot" width="600">

### Kurze Beschreibung:

Es soll eine echte Arbeitsumgebung geschaffen werden, dafür starten wir erstmal mit der Konfiguration der Firewall PFSENSE als virtuelle Maschine
auf einem Windows Server 2025 über HYPER-V

Als zweites erstellen wir über Hyper-V einen virtuellen Windows Server 2025 namens PLABDC01 und werten diesen zu einem Domaincontroller auf.

Als drittes erstellen wir über Hyper-V einen zweiten virtuellen Windows Server 2025 PLABDM01 und treten mit diesem unserer Domain von DC01 bei.

Als viertes erstellen wir über Hyper-V einen Windows 11 Client und treten mit diesem auch der Domain von DC01 bei.

## Firewall Konfiguration:

Als erstes gehen wir auf PFSENSE und forden einmal die kostenlose Version der Firewall an und laden diese herunter

Als nächstes laden wir 7ZIP herunter und entpacken die heruntergeladene Datei, wir benötigt damit wir eine ISO bekommen, die wir benutzen können

Danach erstellen wir einen privaten virtuellen Switch (LAN) in den Hyper-V Einstellungen

Dann erstellen wir die virtuelle Maschine (Firewall) mit der PFSENSE ISO und fügen unter Einstellungen den Netzwerkadapter LAN hinzu,
deaktivieren Secure boot und starten die virtuelle Maschine.

Dann Standard Einstellungen durchgehen

<img src="images/Aufbau.png" alt="Lab Screenshot" width="400">

Hier sieht man einmal wie unserer Aufbau im LAB sein sollte Gateway 10.71.31.254 von unserer Testumgebung, unsere pfSense WAN IP-Addresse
mit 10.71.31.10.

Danach konfigurieren wir unser eigenes LAN mit pfSense IP-Adresse 192.168.0.1, statischer IP-Addresse PLABDC01 mit 192.168.0.2, 
statischer IP-Addresse 192.168.0.3 von PLABDM01 und dann wird später ber DHCP für PLABWIN10 eine IP Adresse per DHCP hinzugefügt.
(Später im LAB über DHCP)


