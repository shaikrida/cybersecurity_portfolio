# Email Attachment Analysis

## Overview

| Field | Details |
|-------|---------|
| **Scenario** | Email Attachment Analysis |
| **Date** | 13 July 2026 |
| **Analyst** | Shaik Rida |
| **Host** | TCM |
| **Email Sample** | sample1.eml |
| **Severity** | High |
| **MITRE ATT&CK Techniques** | T1566.001, T1204.002 |
| **Tools Used** | Thunderbird, Sublime Text, VirusTotal, Cisco Talos Intelligence |

---

## Scenario Description

The email claims to be from **@moss.it** with the subject **"Due Invoice Payment."** It requests urgent payment of invoices and asks the recipient to share payment confirmation by replying to the email. The attached file is presented as a wire transfer document.

---

## Attack Narrative

1. An email is received from **Paolo Reggiani <Paol.Reggiani@moss.it>**.
2. The email creates urgency by stating that the invoices must be settled by the end of the same day.
3. The recipient is instructed to open the attached file, which is presented as a transfer slip, and send payment details directly to the sender after payment.

---

## Investigation Steps

1. Opened the raw `sample1.eml` file using Thunderbird and viewed its message source.
2. Saved the attachment locally and extracted its **SHA256**, **SHA1**, and **MD5** hashes using the terminal.
3. Analyzed the extracted file hashes using **VirusTotal** and **Cisco Talos Intelligence** to verify the attachment's reputation.

---

## Findings

| Time | Field | Value | Significance |
|------|-------|-------|--------------|
| 13-07-2026 22:11:51 | From | Paolo Reggiani \<Paol.Reggiani@moss.it\> | Claimed sender identity |
| 13-07-2026 22:11:52 | To | wpx@protonmail.com | Target recipient email |
| 13-07-2026 22:11:53 | Date | 14 Jan 2020 00:06:05 -0800 | Email sent timestamp |
| 13-07-2026 22:11:54 | Subject | FW: Due Invoice Payment - protonmail.com - Wire Transfer Document | Phishing lure |
| 13-07-2026 22:11:55 | X-Attached | quotation.iso | Suspicious attachment |
| 13-07-2026 22:11:56 | File Hashes | **SHA256:** `75fdb848eac332b4ca7d88f497e7ba7ebbb9a798d825b28cf1f87b9d7149e87f`<br>**SHA1:** `3fe45f8cd20cd7c63e55e3918dac1d3a0d7fb05a`<br>**MD5:** `6aef1d7f88e8aa450a0c604b4caee5ba` | Hashes of the attachment file |

---

## Analysis

1. Analysis of the extracted file hashes using **VirusTotal** and **Cisco Talos Intelligence** identified the attachment as malicious, with detections from multiple security vendors.
2. **`.iso` attachments** are commonly abused to bypass email security filters, making them a common malware delivery mechanism.
3. These findings confirm that the attachment is malicious and that the email is a phishing attempt disguised as an invoice notification.

---

## Indicators of Compromise (IOCs)

| Indicator Type | Value | Significance |
|----------------|-------|--------------|
| **Subject Line** | FW: Due Invoice Payment - protonmail.com - Wire Transfer Document | Phishing lure. |
| **Possible Malicious Attachment** | `quotation.iso` | Attempt to deliver malware. |
| **Email Body** | *Please find the Due invoices for protonmail.com. These invoices need to be settled urgently. These invoices need to be paid urgently today.* | Urgency-based social engineering tactic to prompt immediate action. |
| **File Reputation** | Detected as malicious by multiple security vendors | Confirms the attachment has a malicious reputation. |

---

## MITRE ATT&CK Mapping

| Technique ID | Technique Name |
|--------------|----------------|
| **T1566.001** | Spear phishing Attachment |
| **T1204.002** | User Execution: Malicious File |

---

## Screenshots

| Screenshot | Description |
|------------|-------------|
| 1_thunderbird | Email sample opened in Thunderbird |
| 2_attachment | Attachment saved to the device |
| 3_hashes | Extracted SHA256, SHA1, and MD5 hashes |
| 4_virustotal | VirusTotal attachment analysis |
| 5_virustotal1 | Additional VirusTotal analysis |
| 6_talosintelligence | Cisco Talos Intelligence analysis |

---

## Conclusion

The analysis demonstrated that email attachments can be used as a delivery mechanism for phishing and malware. Inspecting file properties, content, and reputation is essential to identify potential threats before interacting with email attachments.

---

**Investigated by:** Shaik Rida  
**Role:** SOC Analyst
