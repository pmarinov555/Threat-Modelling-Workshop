# Kill Chain Attack Description: Machine Process & Data Lake Compromise

## Stages of the Attack

### Origins
The attacker targets Solaris Health 360’s AI diagnostic capabilities, exploiting the integration between its medical data lake and machine learning processes to corrupt patient diagnoses.

### Reconnaissance
The attacker profiles:
- Unsecured data ingestion APIs (e.g., DICOM image upload endpoints)
- ML training pipeline tools (e.g., Kubeflow, MLflow)
- Data validation gaps in preprocessing workflows

### Weaponization
- **Poisoned Datasets**: Craft medical images with adversarial perturbations (e.g., cancer CT scans with hidden noise patterns)
- **Model Backdoors**: Develop tampered model weights that misclassify specific patient cohorts

### Delivery
Exploit misconfigured data lake permissions to:
1. Inject poisoned datasets via unauthenticated API endpoints
2. Replace legitimate training jobs with malicious pipeline configurations

### Exploitation
- Bypass anomaly detection using "clean-label" attacks (malicious data that passes validation)
- Abuse automated retraining workflows to deploy corrupted models

### Installation
- Embed persistent backdoors in the model registry (e.g., PyTorch model files with trigger-based misclassification)
- Compromise data version control to enable future reinfection

### Actions on Objectives
- **Clinical Harm**: Cause false negative diagnoses for high-risk patients
- **Data Sabotage**: Degrade model accuracy to undermine trust in Solaris Health 360
- **Extortion**: Threaten to sustain attacks unless ransom is paid

```mermaid
flowchart LR
    A[Reconnaissance] -->|Map data lake APIs| B[Weaponization]
    B -->|Create poisoned DICOMs| C[Delivery]
    C -->|Exploit S3 write ACLs| D[Exploitation]
    D -->|Bypass data validation| E[Installation]
    E -->|Backdoor model registry| F[Actions]
    F -->|False diagnoses| G[Patient Harm]
    F -->|Model degradation| H[Reputation Damage]
    
    style A fill:#F4D03F
    style B fill:#E74C3C
    style C fill:#EB984E
    style D fill:#DC7633
    style E fill:#BA4A00
    style F fill:#922B21