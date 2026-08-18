<div align="center">

# System-Hacking-and-Defense-Simulation
Red team/blue team cybersecurity capstone: full attack lifecycle (Recon to Exploitation) and defense (Hardening, Detection) in an isolated lab, using STRIDE/DREAD threat modeling and MITRE ATT&amp;CK mapping

### A Complete Red Team vs Blue Team Cybersecurity Lab

![Platform](https://img.shields.io/badge/Platform-VirtualBox-blue)
![OS](https://img.shields.io/badge/Windows%20Server-2022-green)
![OS](https://img.shields.io/badge/Kali-Linux-red)
![Detection](https://img.shields.io/badge/Wazuh-SIEM-orange)
![NIDS](https://img.shields.io/badge/Suricata-IDS-yellow)
![Monitoring](https://img.shields.io/badge/Sysmon-Microsoft-blue)
![Framework](https://img.shields.io/badge/MITRE-ATT%26CK-red)
![ThreatModel](https://img.shields.io/badge/Threat-STRIDE%20%7C%20DREAD-success)

</div>

---

# Project Overview

This project demonstrates an end-to-end cybersecurity assessment performed inside an isolated virtual laboratory. It simulates a realistic attack against a vulnerable Metasploit and Windows Server, followed by detection, monitoring, system hardening, and validation through repeated testing.

The project combines offensive security techniques with defensive monitoring to illustrate how attacks can be detected, analyzed, and mitigated using industry-standard tools.

---

# Objectives

- Build an isolated penetration testing laboratory.
- Discover vulnerable services.
- Perform vulnerability assessment.
- Execute controlled exploitation.
- Detect attacker activity.
- Harden the target system.
- Compare security posture before and after mitigation.
- Map attacks to MITRE ATT&CK.
- Perform STRIDE and DREAD threat modeling.

---

# Lab Architecture

(Add your architecture image here)

```
                         ISOLATED VIRTUALBOX INTERNAL NETWORK
                                  192.168.80.0/24
                                         │
                  ┌──────────────────────┼──────────────────────┐
                  │                      │                      │
                  ▼                      ▼                      ▼
        ┌─────────────────┐    ┌─────────────────┐    ┌─────────────────────┐
        │    Kali Linux   │    │ Windows Server  │    │    Metasploitable   │
        │  ATTACKER VM    │    │      2022       │    │      TARGET VM      │
        │                 │    │   TARGET VM     │    │                     │
        │ • Nmap          │    │ • Sysmon        │    │ • Vulnerable        │
        │ • Nikto         │    │ • Suricata      │    │   Services          │
        │ • Enumeration   │    │ • Wazuh Agent   │    │ • Wazuh Monitoring  │
        │ • Attack Tools  │    │                 │    │                     │
        └────────┬────────┘    └────────┬────────┘    └──────────┬──────────┘
                 │                      │                        │
                 │                      │                        │
                 │      ATTACKS         │                        │
                 ├─────────────────────►│                        │
                 │                      │                        │
                 └─────────────────────────────────────────────► │
                                        │                        │
                                        │                        │
                              Telemetry / Logs                   │
                                        │                        │
                                        └────────────┬───────────┘
                                                     │
                                                     ▼
                                         ┌──────────────────────┐
                                         │    Wazuh Manager     │
                                         │      Separate VM     │
                                         │──────────────────────│
                                         │ • Log Collection     │
                                         │ • Event Correlation  │
                                         │ • Alert Generation   │
                                         │ • MITRE ATT&CK       │
                                         └──────────┬───────────┘
                                                    │
                                                    ▼
                                         ┌──────────────────────┐
                                         │   Wazuh Dashboard    │
                                         │──────────────────────│
                                         │ • Security Alerts    │
                                         │ • Sysmon Events      │
                                         │ • Suricata Events    │
                                         │ • Investigation      │
                                         └──────────────────────┘
```

---

# Technology Stack

| Category | Tools |
|-----------|-------|
| Virtualization | Oracle VirtualBox |
| Operating Systems | Kali Linux, Windows Server 2022 |
| Reconnaissance | Nmap, Nikto |
| Vulnerability Assessment | Nessus Essentials |
| Exploitation | MSFVenom, NTLMRelayX |
| Detection | Sysmon, Suricata |
| SIEM | Wazuh |
| Threat Modeling | STRIDE, DREAD |
| Framework | MITRE ATT&CK |

---

# Attack Workflow

```
Build Isolated Lab
        │
        ▼
Reconnaissance
        │
        ▼
Service Enumeration
        │
        ▼
Vulnerability Assessment
        │
        ▼
Controlled Exploitation
        │
        ▼
Evidence Collection
        │
        ▼
Threat Modeling
        │
        ▼
Deploy Detection
        │
        ▼
System Hardening
        │
        ▼
Repeat Attack
        │
        ▼
Compare Security Improvements
```

---

# Project Structure

```text
System-Hacking-and-Defense-Simulation/
├── architecture
├── lab-setup
├── reconnaissance
├── vulnerability-assessment
├── exploitation
├── detection
├── hardening
├── before-after
├── threat-model
├── mitre
├── report
├── presentation
└── demo
```

---

# Attack Timeline

✔ Reconnaissance

✔ Port Scanning

✔ Service Enumeration

✔ Vulnerability Assessment

✔ Exploitation

✔ Reverse Shell

✔ Detection using Sysmon

✔ Detection using Suricata

✔ SIEM Correlation using Wazuh

✔ Windows Hardening

✔ Attack Validation

---

# Threat Modeling

- STRIDE Analysis
- DREAD Risk Assessment
- Data Flow Diagram
- Risk Prioritization

---

# MITRE ATT&CK Mapping

| Attack Phase | Technique |
|--------------|-----------|
| Reconnaissance | T1595 |
| Service Discovery | T1046 |
| Initial Access | T1190 |
| Command Execution | T1059 |
| Credential Access | T1110 |
| Privilege Escalation | T1068 |

---

# Detection Components

### Sysmon

- Process Creation
- Network Connections
- PowerShell Activity

### Suricata

- Port Scan Detection
- SMB Traffic Monitoring
- Network Intrusion Detection

### Wazuh

- Log Collection
- Event Correlation
- Alert Visualization
- MITRE Mapping

---

# Security Hardening

- Enabled SMB Signing
- Updated Password Policy
- Windows Firewall Configuration
- Microsoft Defender Configuration
- Reduced Attack Surface

---

# Before vs After

| Assessment | Before | After |
|------------|--------|-------|
| Detection | Partial | Comprehensive |
| Attack Success | High | Reduced |
| Monitoring | Limited | Enhanced |

---

# Evidence

- Nmap Scan
- Nessus Report
- Nikto Scan
- Metasploit Session
- Sysmon Events
- Suricata Alerts
- Wazuh Dashboard
- MITRE Navigator

---

# Key Learnings

- Vulnerability assessment methodology
- Offensive security techniques
- Defensive monitoring
- Threat modeling
- MITRE ATT&CK mapping
- Windows hardening
- SIEM integration

---

# Future Improvements

- Active Directory Environment
- Atomic Red Team
- Sigma Rules
- Security Onion
- Automated Attack Simulation
- Purple Team Exercises

---

# Disclaimer

This project was conducted exclusively inside an isolated virtual laboratory using systems owned by the author. All testing was performed for educational and defensive research purposes (C-DAC Project).

---

# Author

**Rishabh Bhosale and Eclipse-X (Team)**

Cybersecurity | Red Team | Vulnerability Assessment | Threat Detection | SOC
