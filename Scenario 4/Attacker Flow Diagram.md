# Attacker Flow Diagram: Insider Attack Targeting Quant Algorithms

sequenceDiagram
    participant Insider
    participant QuantAlgorithmRepo
    participant BackendServer
    participant ExternalServer

    activate Insider
    Insider->>QuantAlgorithmRepo: Abuse privileged access
    QuantAlgorithmRepo->>Insider: Access granted
    deactivate Insider

    activate Insider
    Insider->>QuantAlgorithmRepo: Copy proprietary algorithms
    QuantAlgorithmRepo->>Insider: Algorithms extracted
    deactivate Insider

    activate Insider
    Insider->>ExternalServer: Exfiltrate algorithms via encrypted channels
    ExternalServer->>Insider: Data received
    deactivate Insider

    activate Insider
    Insider->>BackendServer: Modify algorithms to introduce biases
    BackendServer->>QuantAlgorithmRepo: Corrupted algorithms deployed
    deactivate Insider