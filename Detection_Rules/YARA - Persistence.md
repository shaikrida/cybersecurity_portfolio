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

Investigated by: Shaik Rida
Role: SOC Analyst
