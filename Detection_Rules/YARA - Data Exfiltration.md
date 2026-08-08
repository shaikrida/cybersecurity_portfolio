# YARA Rule – Exfiltration Detection

## Detection Logic

The rule checks for indicators associated with DNS and HTTP-based exfiltration, including `dns`, `exfil-data`, `attacker.com`, `nslookup`, and `curl`.

## YARA Rule

```yara
rule exfiltration
{
    meta:
        description = "detects DNS/HTTP exfiltration"
        author = "rshaik"

    strings:
        $a = "dns"
        $b = "exfil-data"
        $c = "attacker.com"
        $d = "nslookup"
        $e = "curl"

    condition:
        any of them
}
```

## Screenshot

<img width="717" height="359" alt="image" src="https://github.com/user-attachments/assets/099210b1-352a-48b8-a9e4-01748bb38ebb" />


Investigated by: Shaik Rida  
Role: SOC Analyst
