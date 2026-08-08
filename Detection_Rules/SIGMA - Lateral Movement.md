# Sigma Rule – Lateral Movement Detection

## Detection Logic

The rule detects SSH authentication activity associated with lateral movement, including `Failed password`, `ssh`, and `Invalid user`.

## Sigma Rule

```yaml
title: Suspicious Lateral Movement detection
id: 103
status: testing
description: detects SSH authentication attempts
author: rshaik
date: 2026-05-26

logsource:
  product: linux
  service: sshd

detection:
  selection:
    message:
      - "Failed password"
      - "ssh"
      - "Invalid user"
  condition: selection

level: medium

tags:
  - attack.lateral_movement
  - attack.t1021
```

## Screenshot

<img width="695" height="591" alt="image" src="https://github.com/user-attachments/assets/b83bee02-9b54-43e7-b1f3-d6b5b8b1aad3" />


Investigated by: Shaik Rida  
Role: SOC Analyst
