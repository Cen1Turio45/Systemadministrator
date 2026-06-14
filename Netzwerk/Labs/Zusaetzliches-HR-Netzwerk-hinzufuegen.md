# Lab 3 - Zusätzliches HR-Netzwerk hinzufügen

<img src="images/Lab.png" alt="Lab Screenshot" width="600">

## Ziel

Ein zusätzliches internes Netz `HR` in Hyper-V und pfSense einbinden.

## Netzbereiche

| Netz | Zweck | IP-Bereich |
| --- | --- | --- |
| WAN | externes Netz | `10.71.31.0/24` |
| LAN | internes Basisnetz | `192.168.0.0/24` |
| HR | neues internes Netz | `192.168.2.0/24` |

## pfSense Interfaces

| Interface | Adapter | IP-Adresse | Gateway |
| --- | --- | --- | --- |
| WAN | `hn0` | `10.71.31.2/24` | `10.71.31.254` |
| LAN | `hn1` | `192.168.0.1/24` | keines |
| HR | `hn2` | `192.168.2.1/24` | keines |

## Checkliste

- pfSense herunterfahren.
- Privaten Hyper-V-Switch `HR` erstellen.
- pfSense-VM um dritten Netzwerkadapter für `HR` erweitern.
- Interface in pfSense zuweisen, aktivieren und in `HR` umbenennen.
- HR-IP statisch setzen: `192.168.2.1/24`.
- Outbound NAT für `LAN` und `HR` prüfen.
- Firewall-Regel für `HR` bewusst setzen.
- Testserver in den HR-Switch verschieben.
- IP-Konfiguration, Gateway, DNS und Erreichbarkeit prüfen.

## Worauf man achten muss

- Neues Interface braucht eigene Firewall-Regeln, sonst ist es blockiert.
- NAT-Regeln müssen das neue Netz berücksichtigen.
- Gateway bleibt auf pfSense, nicht auf einem internen Server.
- Nach Netzwechsel DNS und Domänenkommunikation testen.

## Ergebnis

Das HR-Netz ist logisch getrennt und über pfSense kontrollierbar.
