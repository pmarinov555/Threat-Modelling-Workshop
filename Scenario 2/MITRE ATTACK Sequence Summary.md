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
    style Poison fill:#E74C3C

    Recon["Reconnaissance (TA0043): Scan data pipeline APIs"] --> Poison["Weaponization (T1647): Craft poisoned DICOM images"]
    Poison --> Deliver["Delivery (T1530): Exploit unauthenticated data API"]
    Deliver --> Exploit["Exploitation (T1574): Bypass data validation"]
    Exploit --> Install["Installation (T1600): Embed backdoor in model"]
    Install --> C2["C2 (T1102): Exfil via model metadata"]
    C2 --> Impact["Impact (T1565): Corrupt patient diagnoses"]

    subgraph MITRE_Techs
        T1[[T1530 - Container Administration Command]]
        T2[[T1574 - Hijack Execution Flow]]
        T3[[T1647 - Adversarial ML]]
    end