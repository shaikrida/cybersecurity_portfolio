# Sigma Rule – Exfiltration Detection

## Detection Logic

The rule detects indicators associated with DNS or HTTP-based outbound exfiltration activity, including `nslookup`, `dns`, `http`, `exfil-data`, `curl`, and `attacker.com`.

## Sigma Rule

```yaml
title: Suspicious exfiltration detection
id: 104
status: testing
description: detects DNS or HTTP outbound activity indicating exfiltration
author: rshaik
date: 2026-05-26

logsource:
  product: linux
  service: syslog

detection:
  selection:
    message:
      - "nslookup"
      - "dns"
      - "http"
      - "exfil-data"
      - "curl"
      - "attacker.com"
  condition: selection

level: high

tags:
  - attacker.exfiltration
  - attacker.t1048
  - attacker.t1041
```

## Screenshot

<img width="863" height="626" alt="image" src="https://github.com/user-attachments/assets/6b0cc549-d98b-4bad-8967-f47b257213e6" />


Investigated by: Shaik Rida  
Role: SOC Analyst
