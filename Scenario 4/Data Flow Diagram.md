```mermaid
erDiagram
    QUANT_RESEARCHER ||--o{ ALGORITHM : "develops"
    ALGORITHM ||--|{ VERSION : "has"
    ALGORITHM }|..|{ BACKEND : "executed in"
    BACKEND ||--o{ TRADING_SYSTEM : "feeds data to"
    QUANT_RESEARCHER }|..|{ EXTERNAL_STORAGE : "exfiltrates to"