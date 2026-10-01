# Network forensics: Norvex packet capture

Forensic analysis carried out by ZCorp on a packet capture provided by the fictional company Norvex.

## Context

On 7 December 2024, the Norvex IT team noticed suspicious traffic on its internal network and engaged ZCorp to investigate the captured network log. During the analysis, a disclosure of employee personal data was found, which Norvex was advised to report to the CNIL. Affected people were notified and measures were taken.

An FTP server used for file sharing had not been secured for lack of resources, leaving FTP traffic in cleartext on the network.

## Tools

- Wireshark 4.0.17 (frame analysis)
- md5sum (hashing of evidence and attachments)
- A running log (main courante) and a hash table of the attachments

## Analysis

The first goal was to find suspicious traffic: unexpected ARP, cleartext data disclosure, or automatic authentication. FTP frames were observed between two machines:

- 192.168.0.52
- 192.168.0.55

The two machines communicated without encryption, and files about employees, emails, and company documents were transferred in cleartext, so any machine on the network could read them.

The client confirmed the addresses belonged to a VMware virtual machine and an FTP server. The cleartext communication also exposed authentication requests from the VM to the FTP server using credentials unknown to the company, which the Norvex IT team confirmed as malicious activity.

## Findings and measures

- **Short term**: personal data breach declared to the CNIL, users reset their passwords (minimum 12 characters, upper and lower case, digits, symbols), the rogue FTP account `pirate12` was removed, and the FTP server was cut off in favor of a temporary managed file-sharing solution. As requested by Norvex, the capture and all copies are deleted once the incident is closed.
- **Long term**: migrate FTP to SFTP to encrypt file transfers, and add a SOC to detect suspicious traffic and configuration weaknesses proactively.
