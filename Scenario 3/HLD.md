```mermaid
flowchart TD
    subgraph "Web Tier"
        WT1[Patient Portal] --> WT2[Appointment API]
    end

    subgraph "Database Tier"
        DT1[(Patients DB)] --> DT2[(Prescriptions DB)]
    end

    subgraph "Attack Path"
        AP1[SQLi Vector] -.-> WT2
        WT2 -.-> DT1
        DT1 -.-> EXFIL[C2 Server]
    end

    WT1 -->|Legit queries| DT1
    WT2 -->|Valid transactions| DT2