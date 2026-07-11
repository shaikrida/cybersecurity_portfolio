# Email Header and Sender Analysis

## OVERVIEW

| Field | Details |
|-------|---------|
| **Scenario** | Email Header and Sender Analysis |
| **Date** | 10 July 2026 |
| **Analyst** | Shaik Rida |
| **Host** | TCM |
| **Email Sample** | sample1.eml |
| **Severity** | Medium-High |
| **MITRE ATT&CK Techniques** | T1566.001, T1204.002 |
| **Tools Used** | Thunderbird, Sublime Text, WHOIS Lookup, Message Header Analyzer |

---

## SCENARIO DESCRIPTION

The email claims to be from Chase Online Services regarding the blocking of a bank account due to unusual activities and contains an attachment that supposedly restores access to the account.

---

## Attack Narrative

1. Victim receives an email impersonating Chase Online Services.
2. The email creates urgency by stating the account has been temporarily suspended.
3. The victim is instructed to open the attachment to reactivate and verify the account.

---

## Investigation Steps

1. Opened the raw `sample1.eml` file using Thunderbird and viewed its message source.
2. Used Sublime Text to improve the readability of the message source.
3. Performed a WHOIS lookup on the sender's server IP address to verify ownership and compare it with the claimed sender domain.
4. Analyzed the message source using a Message Header Analyzer.

---

## Findings

| Time | Field | Value | Significance |
|------|-------|-------|--------------|
| 11-07-2026 00:46:53 | From | alerts@chase.com | Claimed sender identity |
| 11-07-2026 00:46:55 | To | Bob Sanders \<bob.sanders@corhalitech.com\> | Target recipient email |
| 11-07-2026 00:46:58 | Date | Wed, 01 May 2024 20:04:05 +0000 | Email sent timestamp |
| 11-07-2026 00:47:02 | Subject | Your Bank Account has been blocked due to unusual activities | Phishing lure |
| 11-07-2026 00:47:03 | Message-ID | `<i7g9MMh5NtErtaOzQZEp3D-i-u3FWwdo0wY5mhD8Q1vIvv1yeLj...@protonmail.com>` | Unique email identifier |
| 11-07-2026 00:47:05 | X-Sender-IP | 185.70.40.140 | Sender server IP |

---

## Analysis

1. Analysis of the raw email headers exposed the true **From**, **Return-Path**, and **Received** fields that are hidden in the normal email view.
2. The WHOIS lookup identified the owner of the originating IP address, **185.70.40.140**, while the Message Header Analyzer confirmed the complete email delivery path. Together, these findings revealed that the email did not originate from the claimed **Chase Online Services** domain. Instead, the sender IP belonged to **Proton Technologies**, indicating that the email was sent from a spoofed server.

---

## MITRE ATT&CK Mapping

| Technique ID | Technique Name |
|--------------|----------------|
| T1566.001 | Spear phishing Attachment |
| T1204.002 | User Execution: Malicious File |

---

## Screenshots

| Screenshot | Description |
|------------|-------------|
| 1_thunderbird | Email sample opened in Thunderbird |
| 2_sublime_text | Message source details |
| 3_WHOIS_lookup | WHOIS lookup showing sender server IP owner |
| 4_message_header_analyzer | Message header analysis summary |

---

## Conclusion

Header-level analysis of the sample email revealed a mismatch between the claimed sender domain and the actual originating IP address identified through WHOIS lookup, confirming that the email was spoofed. This investigation highlights the importance of verifying email headers, sender IP addresses, and the delivery path when analyzing suspected phishing emails.

---

**Investigated by:** Shaik Rida  
**Role:** SOC Analyst
