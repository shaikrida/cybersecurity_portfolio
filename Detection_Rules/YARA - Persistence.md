# YARA Rule – Persistence Detection

## Detection Logic

The rule checks for indicators associated with cron-based persistence, including the persistence script path, `crontab`, and a cron schedule pattern.

## YARA Rule

```yara
rule persistence
{
    meta:
        description = "detects cron-based persistence"
        author = "rshaik"

    strings:
        $a = "/tmp/persist.sh"
        $b = "crontab"
        $c = "* * * * *"

    condition:
        any of them
}
```
## Screenshot
<img width="650" height="279" alt="image" src="https://github.com/user-attachments/assets/5c214580-74c7-4f1f-811c-47cb4f10f5c0" />


Investigated by: Shaik Rida  
Role: SOC Analyst
