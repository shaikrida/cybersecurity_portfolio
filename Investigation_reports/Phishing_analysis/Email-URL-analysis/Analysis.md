# Email URL Analysis

## Overview

| Field | Details |
|-------|---------|
| Scenario | Email URL Analysis |
| Date | 13 July 2026 |
| Analyst | Shaik Rida |
| Host | TCM |
| Email Sample | sample1.eml |
| Severity | Medium-High |
| MITRE ATT&CK Techniques | T1566.001, T1204.002 |
| Tools Used | Thunderbird, Sublime Text, CyberChef, Virustotal, urlscan.io, wannabrowser, url2png |

---

## Scenario Description

The email claims to be from Chase Online Services regarding the blocking of a bank account due to unusual activities and contains an attachment that supposedly restores access to the account.

---

## Attack Narrative

1. An email impersonating Chase Online Services is received.
2. The email creates urgency by stating the account has been temporarily suspended.
3. The receipient is instructed to open the attachment to reactivate and verify the account.

---

## Investigation Steps

1. Opened the raw **sample1.eml** file using Thunderbird and viewed its message source.
2. Used Sublime Text to improve the readability of the message source to find the http browser link that takes us to the page as given.
3. The encoding used was found to be from quoted printable, so CyberChef was used decode it.
4. The URL was analysed using different URL analysis tools like virustotal, urlscan.io, url2png and wannabrowser.

---

## Findings

| Time | Field | Value | Significance |
|------|-------|-------|--------------|
| 13-07-2026 21:22:12 | From | alerts@chase.com | Claimed sender identity |
| 13-07-2026 21:22:13 | To | Bob Sanders <bob.sanders@corhalitech.com> | Target recipient email |
| 13-07-2026 21:22:15 | Date | Wed, 01 May 2024 20:04:05 +0000 | Email sent timestamp |
| 13-07-2026 21:22:21 | Return-path | kellyellin426@proton.me | Receiver address |
| 13-07-2026 21:22:23 | X-Sender-IP | 185.70.40.140 | Sender server IP |
| 13-07-2026 21:22:30 | URL | https://dsgo.to/CQECQECnpqY3NDSGtODt9ft2qtxzcXGUveTV5fRYmtYAZsQCnpqY3NDSGtODt9ft2qtxzcXGUveTV5fRYmtYAZsQCQECnpqY3NDSGtODt9ft2qtxzcXGUveTV5fRYmtYAZsQ | Page as given in the email |

---

## Analysis

Though the sender domain spoofed as it does not match with the claimed identity on checking the IP address, the URL seems to be legitimate as analysed by the tools.

---

## MITRE ATT&CK Mapping

| Technique ID | Technique Name |
|-------------|----------------|
| T1566.001 | Spear phishing Attachment |
| T1204.002 | User Execution: Malicious File |

---

## Screenshots

| Screenshot | Description |
|------------|-------------|
| 1_thunderbird | Email sample in Thunderbird |
| 2_sublime | Message source in sublime text |
| 3_encoding | Shows type of encoding used |
| 4_cyberchef | Decoding from quoted printable |
| 5_virustotal | URL analysis |
| 6_url2png | URL analysis |
| 7_urlscan | URL analysis |
| 8_wannabrowser | URL analysis |

---

## Conclusion

The URL embedded in the email was extracted, decoded from the Content-Transfer-Encoding format where necessary, and analyzed using multiple URL analysis tools. The analysis traced the complete redirection chain and examined the destination for indicators of phishing or malware. While the redirect itself used legitimate infrastructure, it was found to be part of a phishing campaign designed to deliver a malicious or deceptive payload. Therefore, the embedded URL should be treated as suspicious and malicious within the context of the email.

---

**Investigated by:** Shaik Rida
**Role:** SOC Analyst
