| Risk ID | Description                                         | Severity | Likelihood | Impact | Mitigation Plan                                      |
|---------|-----------------------------------------------------|----------|------------|--------|------------------------------------------------------|
| R2-1    | Unvalidated training data ingestion                | Critical | High       | Critical | Implement GAN-based anomaly detection in data pipeline |
| R2-2    | Model registry without version signing             | High     | Medium     | High    | Enforce code/model signing with hardware security modules |
| R2-3    | Overprivileged service accounts in ML workflows    | High     | High       | Medium  | Apply just-in-time access for training jobs          |