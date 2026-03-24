1. Threat Hunting
Theoretical Concepts

Threat Hunting is a proactive approach where security analysts actively search for hidden threats that may bypass automated detection systems. Unlike reactive incident response, it focuses on identifying suspicious patterns early.

Frameworks used:

SqRR (Search, Query, Retrieve, Respond)
TaHiTI (Targeted Hunting integrating Threat Intelligence)
Data Sources
EDR logs
Network traffic
System event logs
Threat intelligence feeds
Practical Implementation

Steps Performed:

Defined hypothesis for privilege escalation
Queried logs using Event ID 4672
Identified suspicious activity
Mapped to MITRE ATT&CK T1078
Used AlienVault OTX for threat intelligence
Cross-referenced using Velociraptor (SELECT * FROM processes)
Findings
Timestamp	User	Event ID	Notes
2026-03-22	testuser	4672	Admin privilege assigned
Threat Intelligence Integration

AlienVault OTX was used to identify suspicious IP indicators and validate them using Velociraptor queries.

Hunting Report (100 words)

The threat hunting activity focused on identifying unauthorized privilege escalation using Event ID 4672. A hypothesis was developed and validated using log analysis. Threat intelligence from AlienVault OTX was used to identify suspicious indicators, which were further analyzed using Velociraptor queries. The findings were mapped to MITRE ATT&CK technique T1078 (Valid Accounts). The activity demonstrated how proactive threat hunting can identify hidden threats that may bypass automated detection systems. This approach improves early detection and enhances SOC capabilities in identifying potential security breaches.

2. SOAR Automation
Theoretical Concepts

SOAR (Security Orchestration, Automation, and Response) automates SOC workflows. It includes:

Orchestration (tool integration)
Automation (task execution)
Response (incident handling)
Integration
Wazuh (SIEM)
TheHive (incident management)
Practical Implementation

Steps Performed:

Simulated phishing alert in Wazuh
Triggered SOAR playbook
Checked IP reputation
Blocked IP using CrowdSec
Created case in TheHive
Playbook Table
Step	Status	Notes
Check IP	Success	Malicious
Block IP	Success	Blocked
Create Ticket	Success	Created
Playbook Testing

A phishing alert was simulated in Wazuh, and the playbook successfully executed all actions automatically.

Playbook Summary (50 words)

The SOAR playbook automated the phishing response process by validating IP reputation, blocking malicious IP addresses, and creating incident tickets. This reduced manual effort and improved response time. Integration with Wazuh and TheHive enabled seamless workflow execution and efficient incident handling.

3. Post-Incident Analysis
Theoretical Concepts

Post-incident analysis identifies root causes and improves future response. Techniques include:

5 Whys
Fishbone Diagram
Practical Implementation
5 Whys
Question	Answer
Why clicked?	Malicious link
Why trusted?	Legit email
Why not detected?	Weak filtering
Why weak?	No advanced detection
Why missing?	Poor configuration
Fishbone Diagram

A Fishbone Diagram was created using Draw.io to identify causes related to process, technology, and user awareness.

Metrics
MTTD: 2 hours
MTTR: 4 hours
Lessons Learned
Improve email filtering
Train users
Enhance detection rules
Continuous Improvement
Implement advanced security tools
Improve monitoring
Reduce detection time
4. Alert Triage
Theoretical Concepts

Alert triage prioritizes alerts based on severity and impact.

Practical Implementation

Steps:

Reviewed alert
Identified IP
Assigned priority
Validated using VirusTotal
Alert Table
Alert ID	Description	IP	Priority
005	File Download	192.168.1.102	High
Automated Validation

File hash was checked using VirusTotal and confirmed as malicious.

5. Evidence Analysis
Theoretical Concepts

Evidence analysis involves examining logs and maintaining integrity using chain-of-custody.

Tools Used
Velociraptor
FTK Imager
Practical Implementation

Steps:

Collected logs
Analyzed network connections
Identified suspicious IP
Findings
Local	Foreign	Status
192.168.x	185.x	Normal
192.168.x	203.x	Suspicious
Chain of Custody
Item	Description	Collected By	Date	Hash
Log	Network Data	SOC Analyst	2026-03-22	SHA256
6. Adversary Emulation
Theoretical Concepts

Adversary emulation simulates attacker behavior using MITRE ATT&CK.

Tools
MITRE Caldera
Wazuh
Red vs Blue
Red Team: Attacker
Blue Team: Defender
Practical Implementation

Steps:

Simulated phishing attack (T1566)
Generated logs
Detected in SIEM
Table
Timestamp	Technique	Status
2026-03-22	T1566	Detected
Emulation Report (100 words)

The adversary emulation simulated a phishing attack using MITRE ATT&CK technique T1566. The attack was detected by the monitoring system, and alerts were generated in real-time. The SOC team responded efficiently by analyzing and mitigating the threat. This exercise demonstrated the effectiveness of detection mechanisms while highlighting the need for improved early-stage prevention. Adversary emulation helps organizations test their defenses and improve detection capabilities by simulating real-world attack scenarios.

7. Security Metrics
Theoretical Concepts

SOC performance is measured using:

MTTD
MTTR
Dwell Time
False Positive Rate
Metrics
MTTD: 2 hours
MTTR: 4 hours
Dwell Time: 6 hours
False Positive Rate: Low

Executive Report (150 words)

The SOC demonstrated effective performance in detecting and responding to security incidents. The Mean Time to Detect (MTTD) and Mean Time to Respond (MTTR) were within acceptable limits, indicating efficient monitoring and response capabilities. The low false positive rate reflects accurate alerting mechanisms, reducing unnecessary workload on analysts. However, the dwell time indicates that improvements are needed in early detection to minimize the impact of threats. Implementing advanced monitoring systems, enhancing detection rules, and increasing automation can further improve SOC efficiency. Overall, the SOC shows strong operational capability, with opportunities for improvement in proactive threat detection and faster response times.

Continuous Improvement
Improve detection speed
Enhance automation
Reduce false positives
8. Capstone Project
Tools Used
Metasploit
Wazuh
TheHive
CrowdSec
MITRE Caldera
Practical Implementation

Steps:

Simulated attack using Metasploit
Generated logs
Detected in Wazuh
Created alert
Performed triage in TheHive
Blocked IP using CrowdSec
Isolated system
Performed RCA
Detection Table
Timestamp	IP	Attack	MITRE
2026-03-22	192.168.1.102	Samba Exploit	T1210
Response
IP blocked
System isolated
Root Cause

Unpatched vulnerability

Metrics
MTTD: 2 hrs
MTTR: 4 hrs
Executive Summary (300 words)

A simulated cyber attack was conducted using a Samba exploit to represent exploitation of remote services. The attack was initiated using Metasploit and generated logs in the monitoring system. Wazuh successfully detected the attack and generated alerts, which were further analyzed in TheHive. The SOC team performed alert triage and identified the attack as high priority. Immediate response actions were taken, including blocking the attacker’s IP using CrowdSec and isolating the affected system to prevent further compromise.

SOAR automation was used to streamline the response process, reducing manual intervention and improving efficiency. Adversary emulation using MITRE Caldera validated detection capabilities and helped identify potential gaps. Post-incident analysis was conducted using the 5 Whys technique, revealing that the root cause was an unpatched vulnerability.

Security metrics such as MTTD and MTTR indicated effective detection and response, although improvements are needed in early detection to reduce dwell time. Recommendations include implementing regular patch management, improving monitoring systems, and enhancing detection rules.

This capstone project demonstrated a complete SOC workflow, including attack simulation, detection, triage, response, and continuous improvement, highlighting the importance of integrated security operations.
