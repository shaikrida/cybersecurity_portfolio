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
## Screenshot
<img width="614" height="279" alt="image" src="https://github.com/user-attachments/assets/f2e85e56-53b6-43b0-9408-f35a4aa9525c" />


Investigated by: Shaik Rida  
Role: SOC Analyst
