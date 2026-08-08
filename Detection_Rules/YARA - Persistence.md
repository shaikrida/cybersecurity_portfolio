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
<img width="645" height="279" alt="image" src="https://github.com/user-attachments/assets/6ec205ee-3283-4860-b7fb-e2788dda7247" />





Investigated by: Shaik Rida  
Role: SOC Analyst
