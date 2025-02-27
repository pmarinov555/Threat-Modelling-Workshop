# Scenario Comparison Summary 


| Aspect                | Scenario 1 (Phishing)          | Scenario 2 (ML Poisoning)       | Scenario 3 (SQLi)              | Scenario 4 (Insider Attack)                     |  
|-----------------------|---------------------------------|----------------------------------|--------------------------------|-------------------------------------------------|  
| **Initial Access**     | User credentials                | Data pipeline APIs              | Web form inputs                | Privileged credentials (insider)                |  
| **Exploitation Method**| Client-side malware             | Model weight manipulation       | Database query injection       | Abuse of legitimate access + data exfiltration/modification |  
| **Impact Visibility**  | Immediate (data theft)          | Delayed (diagnosis errors)      | Immediate (DB access)          | Delayed (financial loss/IP theft)               |  
| **MITRE ATT&CK Focus** | T1566, T1190                   | T1647, T1574                    | T1190, T1505                   | T1078, T1048, T1059                             |  
| **Compliance Risk**    | HIPAA $164.308(a)(5)(ii)(B)    | HIPAA $164.312(e)(2)(ii)        | HIPAA $164.312(e)(1)           | SOX $302, GDPR Art. 32, FINRA Rule 4370         |  


**Key Notes:**

**Initial Access:**

- Scenarios 1–3 rely on external exploitation (phishing, APIs, web forms).
- Scenario 4 exploits insider privileges, bypassing perimeter defenses.

**Impact Visibility:**

- Insider attacks (Scenario 4) often have delayed detection (e.g., gradual sabotage or hidden exfiltration).

**MITRE Focus:**

- Scenario 4 emphasizes trusted insider abuse (T1078) and data theft (T1048), unlike external techniques like phishing (T1566) or SQLi (T1190).

**Compliance:**

- Scenarios 1–3 focus on HIPAA (healthcare).

- Scenario 4 aligns with financial regulations (SOX, GDPR, FINRA) due to IP theft and algorithmic sabotage.