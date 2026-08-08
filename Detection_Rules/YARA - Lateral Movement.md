# YARA Rule – Lateral Movement Detection

## Detection Logic

The rule checks for indicators associated with SSH-based lateral movement, including `ssh`, `Invalid user`, and `Failed password`.

## YARA Rule

```yara
rule lateral_movement
{
    meta:
        description = "detects ssh activities"
        author = "rshaik"

    strings:
        $a = "ssh"
        $b = "Invalid user"
        $c = "Failed password"

    condition:
        any of them
}
```

## Screenshot
<img width="635" height="323" alt="image" src="https://github.com/user-attachments/assets/8fddc16c-6f84-4774-b23f-9ffe9ef9b5cd" />


Investigated by: Shaik Rida  
Role: SOC Analyst
