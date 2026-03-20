# 1. Threat Hunting

## Objective
To identify suspicious privilege escalation activities using log analysis.

## Hypothesis
Unauthorized users may have gained administrative privileges.

## Methodology
Logs were analyzed using Event ID 4672, which indicates assignment of special privileges.

## Findings

| Timestamp            | User      | Event ID | Notes                     |
|----------------------|----------|----------|---------------------------|
| 2025-08-18 15:00:00  | testuser | 4672     | Unexpected admin access   |

## MITRE ATT&CK Mapping
T1078 – Valid Accounts

## Conclusion
Suspicious privilege escalation was identified, indicating potential misuse of valid credentials.

# 2. SOAR Playbook Development

## Objective
To automate incident response for phishing attacks using a SOAR playbook.

## Playbook Description
A playbook was designed to automatically respond to phishing alerts by validating the IP address, blocking malicious sources, and generating an incident ticket.

## Playbook Steps

| Step                     | Status  | Notes                      |
|--------------------------|--------|----------------------------|
| Check IP Reputation      | Success | IP identified as malicious |
| Block IP                 | Success | 192.168.1.102 blocked      |
| Create Incident Ticket   | Success | Case created               |

## Tools Used
Splunk Phantom (simulated), TheHive

## Conclusion
The playbook successfully automated the response process, reducing manual effort and improving response time.

# 3. Post-Incident Analysis

## Objective
To analyze the root cause of a phishing incident and improve future response strategies.

## Root Cause Analysis (5 Whys)

| Question | Answer |
|----------|--------|
| Why was the email opened? | User clicked malicious link |
| Why was the link clicked? | Email appeared legitimate |
| Why was it not detected? | Weak email filtering |
| Why was filtering weak? | No advanced detection |
| Why not enabled? | Poor configuration |

## SOC Metrics

# 4. Alert Triage

## Objective
To analyze and prioritize security alerts for effective incident response.

## Alert Details

| Alert ID | Description               | Source IP      | Priority | Status |
|----------|--------------------------|----------------|----------|--------|
| 005      | Suspicious File Download | 192.168.1.102  | High     | Open   |

## Analysis
The alert indicates a potentially malicious file download from an internal IP address. The high priority suggests immediate investigation is required.

## Conclusion
The alert was triaged successfully and marked for further investigation.
- Mean Time to Detect (MTTD): 2 hours  
- Mean Time to Respond (MTTR): 4 hours  

## Conclusion
The incident occurred due to weak email security and lack of advanced filtering. Improvements in email security configuration are recommended.

# 5. Evidence Analysis

## Objective
To analyze network connections and identify suspicious activity.

## Analysis Performed
Simulated netstat output was analyzed to identify unusual external connections.

## Findings

| Local Address        | Foreign Address      | Status       |
|---------------------|----------------------|-------------|
| 192.168.1.5:49732   | 185.199.110.153:443  | Normal      |
| 192.168.1.5:49800   | 203.0.113.5:8080     | Suspicious  |

## Chain of Custody

| Item        | Description     | Collected By | Date       | Hash Value |
|-------------|-----------------|--------------|------------|------------|
| Network Log | Connection Data | SOC Analyst  | 2025-08-18 | SHA256     |

## Conclusion
A suspicious connection was identified, indicating possible unauthorized communication with an external server.

# 6. Adversary Emulation

## Objective
To simulate attacker behavior and evaluate SOC detection capabilities.

## Simulation Details

| Timestamp            | TTP                  | Detection Status | Notes                        |
|----------------------|----------------------|------------------|------------------------------|
| 2025-08-18 17:00:00  | T1566 (Phishing)     | Detected         | Email blocked successfully   |

## Tools Used
MITRE Caldera (simulated), Wazuh

## Analysis
The simulated phishing attack was successfully detected and blocked by the security system.

## Conclusion
Adversary emulation helped validate detection mechanisms and improve SOC readiness.

# 7. Security Metrics and Executive Reporting

## Objective
To evaluate SOC performance using key security metrics and present findings.

## Metrics

- Mean Time to Detect (MTTD): 2 hours  
- Mean Time to Respond (MTTR): 4 hours  
- False Positive Rate: Low  
- Dwell Time: 6 hours  

## Analysis
The SOC demonstrated efficient detection and response capabilities. The low false positive rate indicates accurate alerting, while the dwell time suggests room for improvement in early detection.

## Executive Summary
The SOC successfully detected and responded to simulated threats within acceptable timeframes. Automation and proactive threat hunting improved efficiency. However, enhancements in early detection mechanisms can further reduce dwell time and strengthen security posture.

## Conclusion
Security metrics provide valuable insights into SOC performance and help identify areas for continuous improvement.

# 8. Capstone Project: Comprehensive SOC Incident Response

## Objective
To simulate a complete cyber attack scenario and perform detection, triage, response, and analysis.

## Attack Simulation
A Samba vulnerability was exploited using a simulated attack, representing unauthorized remote access.

## Detection

| Timestamp            | Source IP      | Alert Description | MITRE Technique |
|----------------------|----------------|-------------------|-----------------|
| 2025-08-18 16:00:00  | 192.168.1.102  | Samba Exploit     | T1210           |

## Triage
The alert was analyzed and marked as high priority due to potential system compromise.

## Response and Containment
- The affected system was isolated  
- Malicious IP was blocked using simulated firewall controls  

## SOAR Automation
An automated response playbook was executed to block the IP and generate an incident case.

## Root Cause Analysis
The attack exploited a vulnerable service due to outdated system patches.

## Metrics
- MTTD: 2 hours  
- MTTR: 4 hours  
- Dwell Time: 6 hours  

## Executive Summary
A simulated cyber attack exploiting a Samba vulnerability was successfully detected and mitigated by the SOC. The system identified malicious activity through log monitoring and generated alerts for analysis. The incident was triaged as high priority, and immediate response actions were taken, including isolating the affected system and blocking the attacker’s IP address. Automation via SOAR playbooks improved response efficiency. Post-incident analysis revealed that the root cause was an unpatched vulnerability. Metrics such as MTTD and MTTR indicate effective SOC performance, although improvements in proactive patch management and early detection could further enhance security.

## Conclusion
The capstone project demonstrated end-to-end SOC operations, including detection, response, and continuous improvement.
