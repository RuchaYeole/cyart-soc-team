Week 1 – SOC Fundamentals and Monitoring
Objective

The objective of this task was to understand Security Operations Center (SOC) fundamentals and perform practical implementation of log analysis, brute-force detection, alert configuration, intrusion detection, and incident documentation.

Key Concepts Learned
SOC (Security Operations Center)

A Security Operations Center (SOC) is a centralized team responsible for continuously monitoring, detecting, analyzing, and responding to cybersecurity threats.

SIEM (Security Information and Event Management)

SIEM is a system used to collect, aggregate, and analyze logs from multiple sources to detect suspicious activities.

MITRE ATT&CK Framework

Tactic: Credential Access<br>
Technique: T1110 – Brute Force

Practical Work Performed
1. Log Analysis (Event ID 4625)

Generated multiple failed login attempts and analyzed Windows Security Logs by filtering Event ID 4625, which represents failed login attempts.

Observation:<br>
Multiple failed login attempts from IP address 192.168.1.100 indicate potential brute-force activity.

2. SIEM Alert Detection

Configured a detection rule for 5 failed login attempts within 5 minutes and verified alert generation in the SIEM system.

Observation:<br>
The SIEM system generated a critical alert after detecting repeated failed login attempts.

3. Snort IDS Testing

Configured a custom intrusion detection rule and tested it using an HTTP request.

Observation:<br>
Snort successfully detected the defined malicious traffic pattern and generated an alert.

4. Dashboard Monitoring

Created a dashboard to visualize failed login attempts and identify the top source IP generating alerts.

Observation:<br>
The IP address 192.168.1.100 generated the highest number of failed login attempts.

Incident Summary
Field	Value
Event ID	4625
Attack Type	Brute Force
MITRE Technique	T1110
Source IP	192.168.1.100
Severity	Critical
Key Learnings
Understanding of SOC workflow and responsibilities
Practical experience in log analysis and threat detection
Configuration of SIEM-based alert rules
Implementation of intrusion detection using Snort
Preparation of structured incident documentation
  
  Conclusion

This task provided practical exposure to SOC monitoring and detection processes. It strengthened understanding of log analysis, alert generation, intrusion detection, and incident response workflows, which are essential for entry-level SOC analyst roles.
