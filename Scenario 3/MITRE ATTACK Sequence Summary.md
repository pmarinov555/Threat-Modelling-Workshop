# Summary MITRE ATT&CK Sequence

# Attack Description

## Stages of the Attack

### Origins
The attack is initiated by an attacker leveraging a long history of cyber attack techniques. The attacker initiates the attack by identifying potential vulnerabilities in the target system.

### Reconnaissance
The attacker conducts research to identify vulnerabilities and potential targets. This includes gathering information about the target system's infrastructure, software, and potential weaknesses.


```mermaid
flowchart TD
    style Recon fill:#F4D03F
    style Exploit fill:#E74C3C

    Recon["Reconnaissance (TA0043): Identify injection points"] --> Weapon["Weaponization (T1505): Craft SQL payloads"]
    Weapon --> Delivery["Delivery (T1190): Exploit web endpoint"]
    Delivery --> Exploit["Exploitation (T1211): Execute arbitrary SQL"]
    Exploit --> Install["Installation (T1505.001): Create DB backdoor"]
    Install --> C2["C2 (T1048): Exfil via SQL channels"]
    C2 --> Impact["Impact (T1530): Mass data theft"]

    subgraph MITRE_Techs
        T1[[T1190 - Exploit Public-Facing App]]
        T2[[T1505 - SQL Injection]]
        T3[[T1211 - Data Destruction]]
    end