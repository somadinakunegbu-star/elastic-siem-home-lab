# Elastic SIEM Lab

A fully functional Security Operations Center (SOC) lab built using Elastic Stack, Docker, Ubuntu Server, Windows 11, and Kali Linux to simulate enterprise detection engineering and incident response workflows.

---

## Project Status

✅ Complete & Operational

This lab demonstrates a complete, working SIEM pipeline from endpoint instrumentation through alert generation. All components are deployed, data flows end-to-end, and detection rules successfully generate alerts on simulated attacks.

---

## Overview

This project demonstrates how to build an enterprise-grade Security Information and Event Management (SIEM) environment capable of:

- Collecting Windows endpoint telemetry
- Centralizing security logs in Elasticsearch
- Managing endpoints through Elastic Fleet
- Detecting attacker behavior using custom detection rules
- Investigating alerts through Kibana
- Simulating real-world attacks from Kali Linux
- Mapping detections to the MITRE ATT&CK framework

---

## Architecture

```text
                    +----------------------+
                    |      Kali Linux      |
                    |  Attack Simulation   |
                    | (Nmap, Recon, etc.)  |
                    +----------+-----------+
                               |
                               |
                     Network Traffic
                               |
                               v
+--------------------------------------------------------------+

                    Windows 11 Endpoint
                 Sysmon + Elastic Agent Installed

        • Process Creation
        • Network Connections
        • PowerShell
        • Windows Event Logs

+----------------------+-----------------------+---------------+
                       |
                       | Elastic Agent
                       v

               Ubuntu Server (Docker)

      +-----------------------------------------+
      | Elasticsearch                           |
      | Kibana                                  |
      | Fleet Server                            |
      +-----------------------------------------+

                       |
                       v

             Detection Rules & Alerts

                       |
                       v

              Security Investigations
```

---

## Technologies Used

| Category | Technologies |
|----------|--------------|
| SIEM | Elastic Stack (Elasticsearch, Kibana, Fleet) |
| Operating Systems | Ubuntu Server 22.04, Windows 11, Kali Linux |
| Virtualization | VirtualBox |
| Containerization | Docker, Docker Compose |
| Endpoint Telemetry | Elastic Agent, Sysmon |
| Attack Simulation | Nmap, PowerShell |
| Detection Framework | MITRE ATT&CK |
| Version Control | Git, GitHub |

---

## Environment

### Virtual Machines

| VM | Purpose |
|----|---------|
| elastic-server | Elasticsearch, Kibana, Fleet Server |
| endpoint-win | Windows endpoint with Elastic Agent + Sysmon |
| kali-attacker | Attack simulation machine |

---

## Detection Rules Implemented

| Rule | MITRE Technique | Status |
|------|-----------------|--------|
| Nmap Network Scan Detection | T1046 - Network Service Discovery | ✅ Working |
| PowerShell Execution | T1059.001 - PowerShell | ✅ Working |
| Suspicious Process Creation | T1059 | ✅ Working |

---

## Attack Simulation

The following attacks were executed from the Kali Linux VM to validate detections:

- Nmap TCP SYN Scan
- Nmap Service Enumeration
- Host Discovery
- PowerShell command execution
- Process creation events

Each attack successfully generated telemetry and corresponding alerts within Kibana.

---

## Screenshots

### lab-environment

<img width="844" height="483" alt="virtual vm list" src="https://github.com/user-attachments/assets/241a25b3-79ce-4b7b-9bba-74dde6c52309" />


### kibana-home

<img width="1916" height="932" alt="kibana homepage" src="https://github.com/user-attachments/assets/44ee6017-2ce1-4162-ad72-134445636906" />


### fleet-agents

<img width="1914" height="947" alt="healthy agents" src="https://github.com/user-attachments/assets/bbb2d500-297b-4b20-b8b8-f1c88b82c4f2" />


### data-ingestion

<img width="1913" height="935" alt="Data Ingestion" src="https://github.com/user-attachments/assets/c5e2017f-3e6b-4ed6-b1bb-04bf0cf7f9f1" />

### detection-alert

<img width="1919" height="1030" alt="detection" src="https://github.com/user-attachments/assets/5d69f7a6-21c5-4918-b1b2-5fd3abc3f9f3" />



---

## Skills Demonstrated

- Security Operations Center (SOC)
- SIEM Administration
- Detection Engineering
- Threat Detection
- MITRE ATT&CK Mapping
- Windows Event Analysis
- Sysmon Configuration
- Elastic Stack Administration
- Docker
- Linux Administration
- Virtualization
- Incident Investigation
- Log Analysis
- Endpoint Security

---

## Repository Structure

```
elastic-siem-lab/
│
├── README.md
├── architecture/
│   └── architecture-diagram.png
│
├── screenshots/
│   ├── fleet.png
│   ├── alerts.png
│   ├── dashboard.png
│   ├── rules.png
│   └── investigation.png
│
├── detection-rules/
│   ├── nmap-rule.md
│   ├── powershell-rule.md
│   └── suspicious-process.md
│
└── docs/
    ├── setup.md
    ├── attack-simulation.md
    └── investigation.md
```

---

## Learning Outcomes

This project demonstrates the ability to:

- Deploy an enterprise SIEM from scratch
- Configure endpoint telemetry collection
- Manage agents using Elastic Fleet
- Build and validate detection rules
- Simulate attacker techniques
- Investigate alerts using Kibana
- Perform SOC analyst workflows from detection through investigation

---
