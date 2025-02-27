```mermaid
erDiagram
    PATIENT ||--o{ MEDICAL_RECORD : "has"
    MEDICAL_RECORD ||--|{ DATABASE : "stored_in"
    WEB_APP ||--o{ DATABASE : "queries"
    ATTACKER ||--o{ WEB_APP : "injects into"
    ATTACKER ||--o{ DATABASE : "exfiltrates_from"
    DATABASE ||--o{ C2_SERVER : "exports_to"