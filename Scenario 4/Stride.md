```mermaid
graph TD
    subgraph Algorithm_Workflow
        A[Researcher] -->|Modify| B[Algorithm Code]
        B -->|Execute| C[Trading System]
    end

    %% Threats
    T1([Spoofing: Fake researcher account]) -.-> A
    T2([Tampering: Alter algorithm logic]) -.-> B
    T3([Repudiation: Deny code changes]) -.-> D[Audit Logs]
    T4([Info Disclosure: Leak algorithms]) -.-> E[External Storage]
    T5([DoS: Crash trading system]) -.-> C
    T6([Elevation: Unauthorized access]) -.-> F[Admin Panel]

    %% Mitigations
    M1([MFA for repository access]) --> T1
    M2([Code signing + Git history]) --> T2
    M3([Immutable audit logs]) --> T3
    M4([DLP + Encryption]) --> T4
    M5([Resource quota enforcement]) --> T5
    M6([Zero-Trust Architecture]) --> T6