# Windows Server

Kurze Checklisten für typische Windows-Server-Aufgaben.

## Checklisten

| Thema | Fokus |
| --- | --- |
| [Active Directory](Active-Directory-Benutzer-Gruppen-und-Domainbeitritt.md) | Benutzer, Gruppen, Passwort, Accountstatus und Domainbeitritt |
| [Domain Controller demoten](Domain-Controller-demoten.md) | FSMO, Demotion, AD Sites, DNS und alte DC-Referenzen |
| [File-Shares und Berechtigungen](File-Shares-und-Berechtigungen.md) | Share-/NTFS-Rechte, Gruppen und Effective Access |
| [Gruppenrichtlinien prüfen mit gpresult](GPO-Pruefung-mit-gpresult.md) | angewendete, gefilterte und abgelehnte GPOs prüfen |
| [Quick Server Rollouts mit Sysprep](Quick-Server-Rollouts-mit-Sysprep.md) | Master-Image, Sysprep und nicht erneut booten |
| [Windows-11-Erstanmeldung per GPO optimieren](Windows-11-Erstanmeldung-per-GPO-optimieren.md) | OOBE, Cloud-Hinweise, Edge und OneDrive reduzieren |

## PKI

| Thema | Fokus |
| --- | --- |
| [Certificate Template erstellen](Zertifikate-und-PKI/Certificate-Template-erstellen.md) | Template, Subject Name, Sicherheit und Enroll-Rechte |
| [Certificate Template veröffentlichen](Zertifikate-und-PKI/Certificate-Template-veroeffentlichen.md) | Vorlage in der CA aktivieren |
| [Auto-Enrollment Policy](Zertifikate-und-PKI/Auto-Enrollment-Policy.md) | GPO, Template-Rechte und automatische Zertifikate |
| [Zertifikat über MMC anfordern](Zertifikate-und-PKI/Zertifikat-ueber-MMC-anfordern.md) | Computerzertifikat über MMC beziehen |
| [CSR erstellen](Zertifikate-und-PKI/CSR-erstellen.md) | CSR im IIS erstellen |
| [CSR einreichen](Zertifikate-und-PKI/CSR-einreichen.md) | CSR bei Public CA einreichen |
| [Public SSL Certificate](Zertifikate-und-PKI/Public-SSL-Certificate.md) | öffentliches Zertifikat beziehen und installieren |

## Worauf man achten muss

- AD- und DNS-Änderungen haben oft Folgewirkungen.
- Berechtigungen möglichst über Gruppen vergeben.
- Bei GPOs immer Sicherheitsfilterung, WMI-Filter und OU-Pfad prüfen.
- PKI-Probleme sind häufig Template-, Berechtigungs- oder Vertrauenskettenthemen.
