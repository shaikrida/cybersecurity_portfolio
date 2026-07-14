# Dynamic Attachment Analysis

## Overview

| Field | Details |
|-------|---------|
| **Scenario** | Dynamic Attachment Analysis |
| **Date** | 15 July 2026 |
| **Analyst** | Shaik Rida |
| **Host** | TCM |
| **Malware Sample** | BankPaymAdviceVend.Report |
| **Severity** | High |
| **MITRE ATT&CK Techniques** | T1204.002 |
| **Tools Used** | Hybrid Analysis, VirusTotal |

---

## Scenario Description

A malware sample, **BankPaymAdviceVend.Report**, was analyzed using malware analysis tools to identify Indicators of Compromise (IOCs), network indicators, and malicious behavior.

---

## Investigation Steps

1. Opened the malware sample in **Hybrid Analysis** and examined it for IOCs, malicious behavior, and file hashes.
2. Reviewed previous sandbox reports to identify malicious domains, IP addresses, and file hashes associated with the malware sample.
3. Verified the extracted file hash using **VirusTotal** to determine its reputation among security vendors.

---

## Findings

| Time | Field | Value | Significance |
|------|-------|-------|--------------|
| 15-07-2026 00:47:20 | File Reputation | Malicious | File classified as malicious |
| 15-07-2026 00:47:22 | Domain | `tt.vg` | Domain contacted during malware execution |
| 15-07-2026 00:47:25 | IP Address | `172.67.138.42` | Network indicator observed during malware execution |
| 15-07-2026 00:47:28 | Port Number | `443` | HTTPS communication port |
| 15-07-2026 00:47:50 | Labeled As | Trojan.Generic | Malware family identified by the sandbox |
| 15-07-2026 00:48:20 | File Hash | **SHA256:** `2e1408013503cbc13466e2041bd3e045833ce65f5c91b7226e28e27d43d6eaf9` | Unique identifier of the malware sample |

---

## Analysis

1. The malware sample was identified as malicious with a **high threat score** and multiple valid Indicators of Compromise (IOCs).
2. **VirusTotal** reported that **30 out of 61** security vendors detected the sample as malicious.
3. The sample appeared as a legitimate bank payment document but contained hidden malicious content designed to download an additional payload upon execution.

---

## Indicators of Compromise (IOCs)

| Indicator Type | Value | Significance |
|----------------|-------|--------------|
| **File Reputation** | Detected as malicious | Confirms the file is malicious |
| **AV Detection** | 30/61 security vendors | Multiple antivirus engines detected the file as malicious |
| **Processes Observed** | `svchost.exe`, `winword.exe` | Processes observed during malware execution |
| **Domain** | `tt.vg` | Domain contacted during malware execution |
| **Malware Family** | Trojan.Generic | Malware disguised as a legitimate document |
| **Threat Score** | 100/100 | Maximum threat score assigned during sandbox analysis |
| **SHA256 Hash** | `2e1408013503cbc13466e2041bd3e045833ce65f5c91b7226e28e27d43d6eaf9` | Unique identifier used to verify the malware sample and correlate detections |

---

## MITRE ATT&CK Mapping

| Technique ID | Technique Name |
|--------------|----------------|
| **T1204.002** | User Execution: Malicious File |

---

## Screenshots

| Screenshot | Description |
|------------|-------------|
| 1_malware sample | Malware sample |
| 2_hybrid analysis | Hybrid Analysis sandbox results |
| 3_risk assessment | File risk assessment |
| 4_sandbox reports | Previous sandbox reports |
| 5_IOCs | Indicators of Compromise identified |
| 6_virustotal | VirusTotal file hash analysis |

---

## Conclusion

The malware analysis identified suspicious behavior and malicious characteristics, demonstrating the importance of analyzing files before execution to detect potential threats and reduce security risks.

---

**Investigated by:** Shaik Rida  
**Role:** SOC Analyst
