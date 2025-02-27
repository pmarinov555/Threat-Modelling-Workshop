# Kill Chain Attack Description: Insider Attack Targeting Quant Algorithms

## Stages of the Attack

### Abuse of Privileges  
The insider leverages their authorized access to locate and copy proprietary trading algorithms stored in the company repository.

### Data Exfiltration  
Algorithms are encrypted and transferred to external cloud storage or personal devices.

### Sabotage  
The insider modifies algorithm logic to introduce biases (e.g., favoring specific stocks), causing financial losses.

### Covering Tracks  
Audit logs are deleted or altered to hide unauthorized activities.

```mermaid
flowchart LR
A[Abuse Privileges] --> B[Access Algorithm Repository]
B --> C[Exfiltrate Algorithms]
B --> D[Modify Algorithm Logic]
C --> E[Sell to Competitors/Leak]
D --> F[Introduce Biases]
F --> G[Financial Losses]
A --> H[Delete Audit Logs]

style A fill:#F4D03F
style B fill:#E74C3C
style C fill:#EB984E
style D fill:#DC7633
style E fill:#293132
Style F fill:#FF7700
Style G fill:#F1330A
Style H fill:#3366ff