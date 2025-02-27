# Attacker Flow Diagram: Machine Process & Data Lake Attack

```mermaid
sequenceDiagram
    participant Attacker
    participant DataLake
    participant MLProcess
    participant BackendServer
    Patient --> DataLake: Upload medical data

    activate Attacker
    Attacker->>DataLake: Identify unsecured data ingestion API
    DataLake->>Attacker: API endpoint exposed
    deactivate Attacker

    activate Attacker
    Attacker->>MLProcess: Exploit weak model validation workflows
    MLProcess->>Attacker: Training pipeline accessed
    deactivate Attacker

    activate Attacker
    Attacker->>DataLake: Inject poisoned training data
    DataLake->>MLProcess: Retrain model with tainted data
    MLProcess->>BackendServer: Deploy corrupted diagnostic model
    BackendServer->>Patient: Generate false diagnoses
    deactivate Attacker