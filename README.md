# Incident Response and Digital Forensics (DFIR)

A collection of digital forensics and incident response work: a full forensic investigation of a compromised Windows infrastructure, memory forensics challenges with Volatility, and network forensics on a packet capture. The investigation work was carried out under the analyst company name **ZCorp** and is published under the alias **Zeto**.

> All companies, people, and hostnames are fictional (Game of Thrones themed lab accounts). Data comes from isolated lab environments built for defensive training. Contact names and personal data from the original files were removed.

## Executive summary

This portfolio brings together incident response and digital forensics work. The centerpiece is a full forensic investigation of a compromised Windows estate (domain controller, file server, and SQL server), where a stealthy crypto-mining intrusion was reconstructed end to end, mapped to MITRE ATT&CK, and answered with immediate containment measures, remediations, and a costed recovery plan. Alongside it are memory-forensics and network-forensics investigations. Every case follows sound evidence handling (work on a copy, hash everything, keep a running log) and is written for both technical and management readers.

## Contents

| Investigation | Focus | Doc |
|---------------|-------|-----|
| ESSOS crypto-mining intrusion | Full forensic report on three compromised servers (DC, file server, SQL server): timeline, IOCs, remediation, quote | [docs/essos-forensic-investigation.md](docs/essos-forensic-investigation.md) |
| Memory forensics | Volatility 2 and 3 on memory dumps and disk images: process analysis, credential dumping, RDP bitmap cache, BitLocker key extraction | [docs/memory-forensics-volatility.md](docs/memory-forensics-volatility.md) |
| Network forensics | Wireshark analysis of a packet capture: cleartext FTP data exposure and a rogue account | [docs/network-forensics-ftp.md](docs/network-forensics-ftp.md) |
| Endpoint / EDR forensics | SentinelOne alerts, Velociraptor host collection, and memory analysis of a malicious-download intrusion | [docs/endpoint-edr-forensics.md](docs/endpoint-edr-forensics.md) |

## Method

Every investigation follows sound DFIR practice: work on a copy of the copy (never the original), hash all evidence (MD5/SHA-256) to prove integrity, and keep a running log (main courante) of every action, tool, and observation. Findings are mapped to the MITRE ATT&CK framework and written up for both technical and management audiences.

## Tools

Velociraptor, Hayabusa, DFIR-IRIS, Volatility 2 and 3, Wireshark, Sysinternals (procdump), Hashcat, bmc-tools, and standard Linux analysis utilities.

## Skills demonstrated

Forensic acquisition and integrity handling, Windows event log and registry analysis, attack timeline reconstruction, MITRE ATT&CK mapping, indicator of compromise extraction, memory and disk forensics, network traffic analysis, incident reporting (technical and managerial), and remediation planning (containment, eradication, recovery, PCA/PRA, SOC).
