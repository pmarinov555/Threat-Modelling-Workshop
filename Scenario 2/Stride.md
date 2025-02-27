```mermaid
graph TD
    subgraph "Data Lake"
        DL[Data Lake] -->|Processes| ML[ML Training]
    end

    %% Threats
    T1([Spoofing: Fake data sources]) -.-> DL
    T2([Tampering: Poisoned datasets]) -.-> DL
    T3([Repudiation: No data lineage]) -.-> DL
    T4([Info Disclosure: Model inversion]) -.-> ML
    T5([DoS: Training job overload]) -.-> ML
    T6([EoP: Model registry takeover]) -.-> ML

    %% Mitigations
    M1([Signed data provenance]) --> T1
    M2([Immutable storage logs]) --> T2
    M3([Blockchain-backed lineage]) --> T3
    M4([Differential privacy]) --> T4
    M5([GPU quota limits]) --> T5
    M6([Model signing keys]) --> T6