```mermaid
flowchart TD
    subgraph "Data Pipeline"
        DP1[Data Ingestion API] --> DP2[Validation Service]
        DP2 --> DP3[Raw Data Lake]
    end

    subgraph "ML Training"
        ML1[Curated Dataset] --> ML2[Feature Engineering]
        ML2 --> ML3[Model Training]
        ML3 --> ML4[Model Registry]
    end

    subgraph "Attack Surface"
        AS1[Unsecured API] -.-> DP1
        AS2[Model Registry API] -.-> ML4
        AS3[Training Compute] -.-> ML3
    end

    DP3 --> ML1
    ML4 --> Production[Diagnostic Service]