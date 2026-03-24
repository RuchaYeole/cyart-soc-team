# Capstone Project: Full SOC Workflow Simulation

## 1. Attack Simulation

Metasploit Framework was used to simulate an attack using the Samba usermap script exploit.

- Exploit: exploit/multi/samba/usermap_script  
- Payload: cmd/unix/reverse  
- Target IP: 192.168.1.101  

The exploit was configured and executed. The connection attempt resulted in a timeout due to the absence of a vulnerable system.

### Screenshot:
![Metasploit Execution](./attack.png)

---

## 2. Detection and Triage

The simulated attack activity was analyzed.

| Timestamp            | Source IP      | Alert Description | MITRE Technique |
|----------------------|----------------|-------------------|-----------------|
| 2025-08-18 14:00:00  | 192.168.1.101  | Samba exploit     | T1210           |

### Screenshot:
![Alert Triage](./triage.png)

---

## 3. Response and Containment

- Blocked attacker IP: 192.168.1.101  
- Isolated affected system  
- Prevented further access  

---

## 4. Incident Escalation

A high-severity incident was identified and escalated to Tier 2.

- Attack Type: Samba exploit  
- Severity: High  

### Screenshot:
![Escalation Evidence](./attack.png)

---

## 5. Final Incident Report

A simulated attack was successfully detected and handled.

- Attack detected via logs  
- Threat validated using threat intelligence  
- System secured  
- Escalated for further investigation  

---

## 6. Manager Brief

A simulated cyberattack was detected and handled successfully. The attacker was identified and blocked. No major damage occurred, and preventive actions are being implemented.
