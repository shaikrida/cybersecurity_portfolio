# Email Content Analysis

## Overview

| Field | Details |
|-------|---------|
| **Scenario** | Email Content Analysis |
| **Date** | 12 July 2026 |
| **Analyst** | Shaik Rida |
| **Host** | TCM |
| **Email Sample** | sample1.eml, sample4.eml |
| **Severity** | Medium-High |
| **MITRE ATT&CK Techniques** | T1566.001, T1204.002 |
| **Tools Used** | Thunderbird, Sublime Text, CyberChef |

---

# sample1.eml – Spoofed Email

## Scenario Description

The email claims to be from **Trustwallet Support**, stating that the account must be verified or it will be suspended. It contains an attachment that supposedly restores access to the account.

---

## Attack Narrative

1. An email is received from **Trustwallet Support**.
2. The email creates urgency by stating the account will be suspended if not verified by **10/30/2022**.
3. The email instructs the recipient to open the attachment **"Confirm my wallet"** to reactivate and verify the account.

---

## Investigation Steps

1. Opened the raw `sample1.eml` file using Thunderbird and viewed its message source.
2. Used Sublime Text to improve the readability of the message source regarding MIME version, content encoding type, content type, and the email content.
3. Since the email was of **plain text** type, analysis of the email body was performed.

---

## Findings

| Time | Field | Value | Significance |
|------|-------|-------|--------------|
| 12-07-2026 20:48:15 | From | Trustwallet-Support \<7wq1vg3kn9woejk4@emails.gorgias.com\> | Claimed sender identity |
| 12-07-2026 20:48:16 | To | emily.jenkins@potentialsecurity.net | Target recipient email |
| 12-07-2026 20:48:18 | Date | Mon, 31 Oct 2022 07:03:57 +0000 | Email sent timestamp |
| 12-07-2026 20:48:19 | MIME-Version | 1.0 | Mail extension version |
| 12-07-2026 20:48:21 | Content-Transfer-Encoding | 7bit | Type of encoding |
| 12-07-2026 20:48:23 | Content-Type | text/plain; charset=ascii | Text type |
| 12-07-2026 20:48:25 | Subject | FWD: All unverified accounts will be suspended on 10/30/2022. | Phishing lure |

---

## Analysis

1. Analysis of the raw email headers showed the MIME version, content encoding type, content type, and the email content.
2. The email body contained grammatical errors, created urgency, and included a suspicious attachment, indicating a potential phishing attempt.

---

## Indicators of Compromise (IOCs)

| Indicator Type | Value | Significance |
|----------------|-------|--------------|
| **Grammatical Error** | Hi Dear; Customer | Poor grammar may indicate a lack of legitimacy. |
| **Sender Domain** | Trustwallet-Support \<7wq1vg3kn9woejk4@emails.gorgias.com\> | Does not match the official Trust Wallet domain. |
| **Subject Line** | FWD: All unverified accounts will be suspended on 10/30/2022. | Urgency-based social engineering tactic. |
| **Possible Malicious Attachment** | Confirm my wallet | May attempt to deliver malware or steal sensitive information. |
| **Spoofed Organization Name** | Trustwallet-Support | Different from the legitimate **Trust Wallet** branding. |

---

## MITRE ATT&CK Mapping

| Technique ID | Technique Name |
|--------------|----------------|
| T1566.001 | Spearphishing Attachment |
| T1204.002 | User Execution: Malicious File |

---

## Screenshots

| Screenshot | Description |
|------------|-------------|
| 1_sample1 email | Email sample opened in Thunderbird |
| 2_original org | Legitimate original organization |
| 3_sublime sample1 | Message source in Sublime Text |

---

# sample4.eml – Legitimate Email

## Scenario Description

The email claims to be from **Coinbase**, stating that the account is missing some information and requires identity verification to comply with financial regulations. It contains a **"Verify now"** button for account verification.

---

## Attack Narrative

1. An email is received from **Coinbase**.
2. The email requests identity verification by **February 5, 2023**.
3. A **"Verify now"** button is provided to complete the verification process.

---

## Investigation Steps

1. Opened the raw `sample4.eml` file using Thunderbird and viewed its message source.
2. Used Sublime Text to improve the readability of the message source regarding MIME version, content encoding type, content type, and the email content.
3. Since the email was of **HTML** type, CyberChef was used to decode the HTML and UTF-8 encoded content.
4. Analyzed the decoded email body.

---

## Findings

| Time | Field | Value | Significance |
|------|-------|-------|--------------|
| 12-07-2026 21:30:02 | To | archie.smith@syncookies.net | Target recipient email |
| 12-07-2026 21:30:04 | Date | Sun, 05 Feb 2023 13:52:25 -0800 | Email sent timestamp |
| 12-07-2026 21:30:08 | MIME-Version | 1.0 | Mail extension version |
| 12-07-2026 21:30:11 | Content-Transfer-Encoding | Base64 | Type of encoding |
| 12-07-2026 21:30:20 | Content-Type | text/html; charset=utf-8 | HTML email format |

---

## Analysis

1. Analysis of the raw email headers showed the MIME version, content encoding type, content type, and the email content.
2. The email body appeared legitimate, with professional language, consistent branding, and no obvious grammatical errors.

---

## Screenshots

| Screenshot | Description |
|------------|-------------|
| 4_sample4 email | Email sample opened in Thunderbird |
| 5_sublime sample4 | Message source in Sublime Text |
| 6_cyberchef | Base64 decoding of email content |

---

## Conclusion

The analysis showed that phishing emails commonly use urgency, spoofed identities, suspicious links or attachments, and grammatical errors, whereas legitimate emails display consistent branding, verified sender information, and professional content. Careful examination of these indicators helps distinguish malicious emails from genuine communications.

---

**Investigated by:** Shaik Rida  
**Role:** SOC Analyst
