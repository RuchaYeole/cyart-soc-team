# Week 4 - Advanced SOC Operations

This folder contains the implementation of:

- Threat Hunting
- SOAR Automation
- Incident Response
- Adversary Emulation
- Security Metrics

Detailed documentation and screenshots are included.

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
