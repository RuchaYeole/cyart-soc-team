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
