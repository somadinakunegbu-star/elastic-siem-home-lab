# Elastic SIEM SOC Lab

A fully functional Security Operations Center (SOC) lab built using Elastic Stack, Docker, Ubuntu Server, Windows 11, and Kali Linux to simulate enterprise detection engineering and incident response workflows.

---

## Overview

This project demonstrates how to build an end-to-end SIEM environment capable of collecting Windows telemetry, detecting attacker behavior, investigating security events, and documenting incidents using Elastic Security.

The lab simulates both defender and attacker systems inside a virtualized environment and includes custom investigations mapped to the MITRE ATT&CK framework.

---

## Architecture

```
                Mac Host
                    │
        ┌───────────┴───────────┐
        │                       │
 Ubuntu Elastic Server      Windows 11 Endpoint
 Elasticsearch              Sysmon
 Kibana                     Elastic Agent
 Fleet Server               Windows Logs
        │
        │
   Kali Linux
   Attacker VM
```

---

## Technologies Used

- Elasticsearch
- Kibana
- Elastic Fleet
- Elastic Agent
- Docker
- Docker Compose
- Ubuntu Server
- Windows 11
- Kali Linux
- Sysmon
- VirtualBox
- SSH
- Git
- GitHub

---

## Features

- Elastic Stack deployment with Docker
- Fleet Server configuration
- Windows endpoint monitoring
- Sysmon telemetry collection
- Windows Event Log ingestion
- Detection engineering using Elastic prebuilt rules
- MITRE ATT&CK mapping
- Security alert investigation
- Incident response documentation
- SOC case management

---

## Detection Scenarios

### PowerShell Execution

MITRE ATT&CK: **T1059.001**

Description:

- Generated malicious PowerShell activity
- Elastic detected execution
- Alert investigated using Timeline
- Incident documented in Kibana Cases

---

### Credential Dumping

MITRE ATT&CK: **T1003**

Description:

- Simulated credential access
- Detection fired successfully
- Reviewed parent processes
- Confirmed expected telemetry

---

## Screenshots

### VirtualBox VM list

<img width="844" height="483" alt="virtual vm list" src="https://github.com/user-attachments/assets/6710e872-f422-472e-9c20-5627450a022c" />


### Kibana Dashboard

(Add screenshot)

---

### Security Alert

(Add screenshot)

---

### Timeline Investigation

(Add screenshot)

---

### Case Management

(Add screenshot)

---

## Repository Structure

```
configs/
notes/
screenshots/
README.md
```

---

## Skills Demonstrated

- SIEM Administration
- Detection Engineering
- Threat Hunting
- Incident Response
- Windows Logging
- Linux Administration
- Docker
- Endpoint Security
- MITRE ATT&CK
- Security Operations
- Network Monitoring

---

## Lessons Learned

Building this lab provided hands-on experience troubleshooting Docker networking, Windows endpoint enrollment, Elastic Fleet configuration, Sysmon integration, and detection validation. It reinforced practical SOC workflows including log analysis, alert triage, investigation, and documentation.

---

## Future Improvements

- Active Directory Domain Controller
- Sigma Rules
- Suricata IDS
- Zeek Network Monitoring
- Custom Detection Rules
- Threat Hunting Dashboards

---

## Author

Somadina Unegbu

Information Technology Student

Towson University

Cybersecurity | SOC | Detection Engineering
