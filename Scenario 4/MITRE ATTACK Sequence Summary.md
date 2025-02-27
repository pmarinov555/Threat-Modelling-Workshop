# Summary MITRE ATT&CK Sequence

## Stages of the Attack

### Origins  
A disgruntled employee with legitimate access to quant algorithms initiates the attack.

### Reconnaissance  
The insider identifies critical algorithms and their storage locations.

### Weaponization  
Prepares scripts to copy algorithms or modifies code to introduce vulnerabilities.

### Exploitation  
Uses privileged credentials to bypass access controls.

### Installation  
Establishes persistence in the system by creating hidden backup accounts.

### Actions on Objectives  
Exfiltrates algorithms to external storage or manipulates them to disrupt trading strategies.

```mermaid
flowchart TD
    Reconnaissance[Reconnaissance] -->|Identify critical algorithms| Weaponization[Weaponization]
    Weaponization -->|Create data exfiltration scripts| Exploitation[Exploitation]
    Exploitation -->|Abuse valid credentials| Installation[Installation]
    Installation -->|Establish persistence| Actions_Objectives[Actions on Objectives]
    Actions_Objectives -->|Sell algorithms| Actions_Objectives
    Actions_Objectives -->|Sabotage trading logic| Actions_Objectives

    subgraph MITRE_Techniques
        Exploitation -->|T1078 - Valid Accounts| MITRE
        Actions_Objectives -->|T1048 - Exfiltration Over Encrypted Channel| MITRE
        Weaponization -->|T1059 - Command-Line Interface| MITRE
    end