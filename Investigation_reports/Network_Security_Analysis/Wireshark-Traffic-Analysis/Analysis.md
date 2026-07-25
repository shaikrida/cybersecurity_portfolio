# Wireshark Traffic Analysis

## Overview

| Field | Details |
|--------|---------|
| Scenario | Wireshark Traffic Analysis |
| Date | 26 July 2026 |
| Analyst | Shaik Rida |
| Platform | TCM Security |
| Malware Sample | `2023-02-03.pcap` |
| Severity | Medium |
| Tools Used | Wireshark, VirusTotal, MalwareBazaar, CyberChef |

---

## Findings

- **Capture Duration:** 02:52:06
- **Protocols Observed:** IP, TCP, HTTP
- **Source IPs:** 10.0.0.6, 10.0.0.149
- **Destination IP:** 128.254.207.55
- **Port Observed:** 80
- **Downloaded File:** `86607.dat`
- **SHA256 Hash:** `713207d9d9875ec88d2f3a53377bf8c2d620147a4199eb183c13a7e957056432`

---

## Traffic Analysis

| Protocol | Observation |
|----------|-------------|
| HTTP | A `.dat` file was downloaded from the remote server. |
| ICMP | Two Echo Requests and two Echo Replies were observed between the communicating hosts. |

---

## Indicators of Compromise (IOCs)

| Indicator | Value |
|-----------|-------|
| Malicious IP | `128.254.207.55` |
| Downloaded File | `86607.dat` |
| File Reputation | Malicious |
| File Type | PE32 executable for MS Windows 4.00 (MZ Header) |
| SHA256 Hash | `713207d9d9875ec88d2f3a53377bf8c2d620147a4199eb183c13a7e957056432` |
| Malware Family | QakBot |
| User-Agent | `curl/7.83.1` |
| Authentication Status | Failed |
| MITRE ATT&CK | T1016 |

---

## Screenshots

| Screenshot | Description |
|------------|-------------|
| Victim IP | Identified victim IP address |
| HTTP Stream | Suspicious User-Agent |
| Downloaded File | Malicious `.dat` file |
| File Hash | SHA256 hash of downloaded file |
| File Reputation | Executable file identified as malicious |
| Malware Family | Detected as QakBot |
| ARP Traffic | Attempt to identify active devices |
| SMTP Stream | TCP stream analysis |
| Credentials | Authentication attempt |
| SMB | Suspicious exported object list |
| VirusTotal IP | Malicious IP reputation |

---

## Conclusion

The packet capture analysis identified suspicious network activity, including the download of a malicious executable associated with the QakBot malware family. The extracted Indicators of Compromise (IOCs) can support threat detection, incident response, and future security monitoring.

---

**Investigated by:** Shaik Rida

**Role:** SOC Analyst
