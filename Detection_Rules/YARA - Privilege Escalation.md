# YARA Rule – Privilege Escalation Detection

## Detection Logic

The rule checks for indicators associated with privilege escalation, including `sudo bash`, `sudo`, and `root`.

## YARA Rule

```yara
rule privilege_escalation
{
    meta:
        description = "detects sudo command execution"
        author = "rshaik"

    strings:
        $a = "sudo bash"
        $b = "sudo"
        $c = "root"

    condition:
        any of them
}
```

Investigated by: Shaik Rida  
Role: SOC Analyst
