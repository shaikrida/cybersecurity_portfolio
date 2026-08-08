# Sigma Rule – Persistence Detection

## Detection Logic

The rule detects indicators associated with cron-based persistence, including `cron`, `crontab`, `persist.sh`, and `/tmp/persist.sh`.

## Sigma Rule

```yaml
title: Suspicious Persistence activity
id: 102
status: testing
description: detects cron command execution or persistence scripts created
author: rshaik
date: 2026-05-26

logsource:
  product: linux
  service: cron

detection:
  selection:
    message:
      - "cron"
      - "crontab"
      - "persist.sh"
      - "/tmp/persist.sh"
  condition: selection

level: high

tags:
  - attack.persistence
  - attack.t1053
```

## Screenshot

<img width="851" height="546" alt="image" src="https://github.com/user-attachments/assets/f1811af4-b9c3-42c0-a1ca-998180c5a6e4" />


Investigated by: Shaik Rida  
Role: SOC Analyst
