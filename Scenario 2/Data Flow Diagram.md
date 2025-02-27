```mermaid
erDiagram
    PATIENT ||--o{ MEDICAL_DATA : generates
    MEDICAL_DATA ||--|{ DATA_LAKE : stored_in
    DATA_LAKE ||--|{ ML_TRAINING : feeds
    ML_TRAINING ||--|{ DIAGNOSTIC_MODEL : produces
    DIAGNOSTIC_MODEL ||--o{ CLINICIAN : assists
    CLINICIAN ||--o{ PATIENT : treats

    ATTACKER ||--|{ DATA_LAKE : poisons
    ATTACKER ||--|{ ML_TRAINING : manipulates