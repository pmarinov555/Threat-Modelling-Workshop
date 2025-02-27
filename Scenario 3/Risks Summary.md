| Risk ID | Description                                         | Severity | Likelihood | Impact | Mitigation Plan                                      |
|---------|-----------------------------------------------------|----------|------------|--------|------------------------------------------------------|
| R3-1    | Unpatched SQL servers                               | Critical | High       | Critical | Monthly DB patching cycles                          |
| R3-2    | Clear-text DB credentials                           | High     | Medium     | High    | Vault-based secret management                       |
| R3-3    | Missing SQL audit trails                            | High     | High       | Medium  | Enable full query logging with alerting             |