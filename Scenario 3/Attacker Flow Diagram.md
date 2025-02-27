# Attacker Flow Diagram: SQL Injection Attack

```mermaid
sequenceDiagram
    participant Attacker
    participant WebApp
    participant Database
    participant CnC

    activate Attacker
    Attacker->>WebApp: Probe /patient/search endpoint
    WebApp->>Attacker: Returns SQL error messages
    deactivate Attacker

    activate Attacker
    Attacker->>WebApp: Send UNION-based payload
    WebApp->>Database: Execute malicious query
    Database->>WebApp: Return schema details
    WebApp->>Attacker: Display database structure
    deactivate Attacker

    activate Attacker
    Attacker->>WebApp: Exploit time-delay SQLi
    WebApp->>Database: Execute WAITFOR DELAY
    Database->>WebApp: Confirm delayed response
    WebApp->>Attacker: Validate vulnerability
    deactivate Attacker

    activate Attacker
    Attacker->>WebApp: Dump patient records
    WebApp->>Database: SELECT * FROM patients
    Database->>CnC: Exfiltrate via DNS tunneling
    CnC->>Attacker: Receive 250k+ PHI records
    deactivate Attacker