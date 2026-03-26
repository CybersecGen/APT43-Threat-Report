# APT34 Threat Analysis

**Organization:** Technology Firm  
**Project Type:** SOC Simulation / Threat Analysis  

---

## Project Overview

This project simulates an APT34-style attack to evaluate how a SOC would detect and respond to advanced threat behaviors.  
Focus: **detection capability, investigation workflow, and security operations readiness** using adversary-informed scenarios.

---

## Challenge

Simulation identified key gaps that would impact SOC detection:

- Limited endpoint visibility  
- Weaknesses in identity and access controls  
- Gaps in monitoring and alerting maturity  
- Low employee threat awareness  

Objective: simulate APT34 behaviors to **strengthen detection and response processes**.

---

## SOC Simulation & Detection Scenarios

### Credential Access (Brute Force / MITRE T1110)
- **Simulated Activity:** repeated login failures on user accounts  
- **Detection Points:** Windows Event ID 4625, SIEM correlation  
- **Investigation Workflow:**
  1. Identify repeated failed logins from same source IP  
  2. Correlate with successful logins (Event ID 4624)  
  3. Flag suspicious accounts for investigation  
- **IOCs:** source IP, targeted usernames  

---

### Execution (Command-Line / PowerShell / MITRE T1059)
- **Simulated Activity:** malicious process execution on endpoints  
- **Detection Points:** Windows Event ID 4688, process command-line monitoring  
- **Investigation Workflow:**
  1. Review parent process and command-line arguments  
  2. Identify unusual scripts or encoded commands  
  3. Map to potential lateral movement attempts  
- **IOCs:** process name, arguments, endpoint hostname  

---

### Privilege Escalation & Persistence
- **Simulated Activity:** unauthorised admin group modifications  
- **Detection Points:** Event logs for group membership changes  
- **Investigation Workflow:**
  1. Review new user and group changes  
  2. Validate against expected admin activity  
  3. Map to risk score for SOC prioritisation  
- **IOCs:** affected accounts, hostnames  

---

## Detection & Response Recommendations

- Implement EDR solutions (simulated endpoints)  
- Monitor key event IDs for authentication and process anomalies  
- Configure SIEM alerts for:
  - Repeated login failures  
  - Suspicious process execution  
  - Unauthorised privilege changes  
- Integrate adversary simulation results into SOC playbooks  

---

## Example Investigation Timeline (Simulation)

 ```text
 10:00 → Multiple failed login attempts on   UserA (Event ID 4625)
 10:05 → Successful login from same IP (Event ID 4624)
 10:10 → Suspicious PowerShell process execution detected (Event ID 4688)
 10:15 → Admin group change simulated on endpoint Host01  
 ```
---

## Key Takeaway

- Adversary simulation improves SOC detection readiness and investigative workflow.
- Mapping behaviors to MITRE ATT&CK and log events enhances threat visibility.
- Structured simulation allows SOC teams to practice detection, correlation, and response safely.
- Lessons learned inform endpoint visibility, alert tuning, and overall SOC effectiveness.
