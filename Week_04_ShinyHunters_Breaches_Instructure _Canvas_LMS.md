# ShinyHunters Breaches Instructure Canvas LMS

## 1) Executive Summary
The hacking group ShinyHunters has compromised the Instructure company behind  Canvas Learning Management System (LMS) , the breach exposed  sensitive user information including names, email addresses, student ID numbers and some private messages between Canvas users .The company officially confirmed the incident, while the attackers launched a public extortion campaign on May 3, 2026.

---

## 2) Attack Timeline
*   **April 29, 2026**: Instructure security teams detect anomalous, unauthorized access within their environment.
*   **May 3, 2026**: ShinyHunters launches a public extortion notice, demanding payment to prevent data leakage (Initial Deadline: May 8, 2026).
*   **May 8, 2026**: Threat actors extend the extortion deadline to May 12, 2026.

---

## 3) MITRE ATT&CK Mapping
*Due to limited technical forensics published by the vendor, the following mapping represents the most probable Tactics, Techniques, and Procedures (TTPs) based on observed behavior:*


| Tactic | Technique | ID |
| :--- | :--- | :--- |
| **Initial Access** | Valid Accounts | T1078 |
| **Impact** | External Defacement | T1491.002  |
| **Collection** | Data from Information Repositories | T1213  |

---

## 4) Detection Opportunities & SIEM Use Cases
*   **Identity Provider (IdP) Monitoring**: Implement SIEM alerts for `Anomalous Authentication` patterns (e.g., Impossible Travel, Unusual Login Times, and Mismatched User-Agent strings) within Cloud IdP logs (Okta, Entra ID).
*   **LMS Application Logs**: Establish behavior baselines to detect bulk data exports or rapid sequential API calls querying Student IDs and Private Messages.
*   **Network/Threat Hunting Indicators (IOCs)**:
    *   `IPv4`: `91[.]215[.]85[.]103`
    *   `URL`: `hxxp://91[.]215[.]85[.]103/pay_or_leak/instructure_affected_schools_list[.]txt`
    *   `Onion Address`: `hxxps://shinyp0g4jjniry5qi824btzn0p6mxhrdtxe2k6pdy4g3vdzqvr[.]onion/`

---

## 5) Recommended Mitigations
*   **M1026 (Privileged Account Management)**: Routinely audit domain, cloud, and local application administrative accounts to restrict lateral movement capabilities.
*   **M1018 (User Account Management)**: Enforce strict Zero-Trust and Least-Privilege models across all SaaS integration layers.
*   **M1047 (Audit)**: Conduct regular credential rotation and access reviews for production database repositories housing institutional PII.

---
## 6) Analyst Notes & Strategic Takeaways

This incident highlights the trade-off between providing scalable and extensible service features and the increased attack surface they introduce. It emphasizes the importance of integrating security considerations early in the design phase to reduce potential exploitation risks.

