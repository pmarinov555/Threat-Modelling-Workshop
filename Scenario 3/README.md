# Kill Chain Attack Description: SQL Injection Data Exfiltration

## Stages of the Attack

### Origins
The attacker targets Solaris Health 360's patient portal, exploiting vulnerable search forms and appointment booking APIs to extract sensitive medical records via SQL injection.

### Reconnaissance
- Map web endpoints: `/patient/search`, `/api/appointments`
- Identify unsanitized input fields (e.g., patient ID, date ranges)
- Probe for error-based SQLi using malformed `GET`/`POST` parameters

### Weaponization
- Craft UNION-based payloads to extract database schema:
  ```sql
  ' UNION SELECT table_name,2,3 FROM information_schema.tables--
- Prepare time-delay blind SQLi for stealthy data extraction:
  ```sql
  ' IF (SELECT COUNT(*) FROM patients) > 1000 WAITFOR DELAY '0:0:5'--

### Delivery
Exploit misconfigured data lake permissions to:
1. Direct browser input on patient portal forms
2. Automated tools (`sqlmap`) against REST APIs
3. Stored XSS vectors forcing SQL execution

### Exploitation
- Extract database credentials from connection pools  
- Dump tables: `patients`,`prescriptions`, `diagnosis_codes`  
- Access HIPAA-covered PHI, including SSNs and treatment histories 

### Installation
- Create Administrative Database Users
- Plant persistent access via SQL Server Agent jobs

### Actions on Objectives
- **Data Theft**: Exfiltrate 250,000+ patient records to attacker-controlled S3 bucket
- **Ransom Demand**: Threaten public release unless Bitcoin payment received
- **System Corruption**: Drop critical tables via DROP DATABASE health360

flowchart LR
    A[Reconnaissance] -->|Find injection points| B[Weaponization]
    B -->|Craft UNION payloads| C[Delivery]
    C -->|Exploit /patient/search| D[Exploitation]
    D -->|Extract DB credentials| E[Installation]
    E -->|Create backdoor users| F[Actions]
    F -->|Mass data exfiltration| G[Data Breach]
    F -->|Database destruction| H[Service Disruption]
    
    style A fill:#F4D03F
    style B fill:#E74C3C
    style C fill:#EB984E
    style D fill:#DC7633
    style E fill:#BA4A00
    style F fill:#922B21