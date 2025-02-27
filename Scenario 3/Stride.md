```mermaid
graph TD
    subgraph "SQL Injection Attack Surface"
        WEB[Web App] --> DB[(Database)]
    end

    %% Threats
    T1([Spoofing: Forged SQL queries]) -.-> WEB
    T2([Tampering: Altered WHERE clauses]) -.-> DB
    T3([Repudiation: No query logging]) -.-> DB
    T4([Info Disclosure: PHI exposure]) -.-> DB
    T5([DoS: Resource-heavy queries]) -.-> WEB
    T6([EoP: sysadmin access]) -.-> DB

    %% Mitigations
    M1([Parameterized queries]) --> T1
    M2([Query whitelisting]) --> T2
    M3([Immutable audit logs]) --> T3
    M4([Column-level encryption]) --> T4
    M5([Query timeout limits]) --> T5
    M6([JIT DB access]) --> T6