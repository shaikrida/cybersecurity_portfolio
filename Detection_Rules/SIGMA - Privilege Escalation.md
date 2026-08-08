# Sigma Rule – Privilege Escalation Detection

## Detection Logic

The rule detects suspicious privilege escalation activity involving `sudo`, `sudo bash`, and `COMMAND=` indicators.

## Sigma Rule

```yaml
title: Suspicious Privilege Escalation
id: 101
status: testing
description: detects sudo/root command execution
author: rshaik
date: 2026-05-26

logsource:
  product: linux
  service: auth

detection:
  selection:
    message:
      - "sudo"
      - "sudo bash"
      - "COMMAND="
  condition: selection

level: high

tags:
  - attack.privilege_escalation
  - attack.t1548
```

## Screenshot

<img width="667" height="583" alt="image" src="https://github.com/user-attachments/assets/6a033545-cfa8-474f-aff9-c13bbe948509" />


Investigated by: Shaik Rida  
Role: SOC Analyst
