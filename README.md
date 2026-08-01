```markdown
# Elastic SIEM SOC Lab

A fully functional Security Operations Center (SOC) lab built using Elastic Stack, Docker, Ubuntu Server, Windows 11, and Kali Linux to simulate enterprise detection engineering and incident response workflows.

---

## Overview

This project demonstrates how to build an end-to-end SIEM environment capable of collecting Windows telemetry, detecting attacker behavior, investigating security events, and documenting incidents using Elastic Security.

The lab simulates both defender and attacker systems inside a virtualized environment and includes custom detection rules for reconnaissance activity.

---

## Architecture

```
                Mac Host (16GB RAM)
                    │
        ┌───────────┼───────────┐
        │           │           │
 Ubuntu Elastic  Windows 11   Kali Linux
 Elasticsearch   Endpoint     Attacker VM
 Kibana          Sysmon       Nmap
 Fleet Server    Elastic Agent Reconnaissance
        │
        └──→ Bridged Network (192.168.1.x)
```

---

## Technologies Used

- Elasticsearch
- Kibana
- Elastic Fleet
- Elastic Agent
- Elastic Defend
- Docker
- Docker Compose
- Ubuntu Server 22.04
- Windows 11
- Kali Linux
- Sysmon (SwiftOnSecurity config)
- VirtualBox
- Nmap
- Git & GitHub

---

## Key Accomplishments

### Elastic Stack SIEM Deployment & Configuration
Architected and deployed a three-VM lab environment (Ubuntu server with Elasticsearch/Kibana, Windows 11 endpoint, Kali Linux attacker VM) on VirtualBox with bridged networking. Configured Docker containers for Elasticsearch and Kibana, deployed Fleet Server for centralized agent management, and enrolled Windows endpoint with Elastic Agent for log collection and forwarding.

### Endpoint Instrumentation & Data Pipeline
Integrated Sysmon with SwiftOnSecurity configuration on Windows endpoint to capture process creation, network connections, and system events. Configured Windows Event Logs integration to collect Sysmon telemetry (`Microsoft-Windows-Sysmon/Operational` channel) and verified end-to-end data flow from endpoint → Elastic Agent → Fleet Server → Elasticsearch → Kibana visualization.

### Attack Simulation & Detection Engineering
Executed Nmap reconnaissance scans from Kali Linux against instrumented Windows endpoint to generate realistic security events. Created Elasticsearch query detection rule (`winlog.event_id:1`) to alert on process creation activity, achieving successful rule execution and alert generation—demonstrating full detection pipeline functionality from telemetry ingestion through alert triggering.

### Incident Investigation & SIEM Analysis
Leveraged Kibana Discover and query language (KQL) to analyze 532+ Sysmon process events, identified attack-related activity patterns, and validated detection rule accuracy. Documented findings in GitHub portfolio repository with architecture diagrams, screenshots, and technical write-ups for demonstration to hiring managers.

---

## Features

- ✅ Elastic Stack deployment with Docker Compose
- ✅ Fleet Server configuration and agent enrollment
- ✅ Windows endpoint instrumentation with Sysmon
- ✅ Windows Event Log ingestion via Elastic Agent
- ✅ Custom Elasticsearch detection rule creation (`winlog.event_id:1`)
- ✅ Nmap reconnaissance attack simulation
- ✅ End-to-end data pipeline validation (532+ events)
- ✅ Alert rule testing and triggering
- ✅ Security event analysis in Kibana
- ✅ MITRE ATT&CK mapping

---

## Detection Scenarios

### Process Creation Detection (Sysmon)

**MITRE ATT&CK:** T1059 (Command and Scripting Interpreter)

**Description:**
- Deployed Sysmon on Windows endpoint with SwiftOnSecurity configuration
- Executed Nmap reconnaissance scans from Kali Linux
- Created Elasticsearch detection rule: `winlog.event_id:1`
- Rule successfully triggered on process creation activity

**Results:**
- ✅ Detection rule enabled and executing (50+ executions)
- ✅ 532+ Sysmon process events collected
- ✅ Alert fired successfully
- ✅ Full detection pipeline validated from telemetry ingestion to alert generation

---

## Screenshots

### VirtualBox VM List
<img width="844" height="483" alt="virtual vm list" src="https://github.com/user-attachments/assets/05622787-4cc8-453d-858e-c28fbc577509" />



### Kibana Homepage
![Kibana Dashboard](https://github.com/user-attachments/assets/6a021d9c-55c9-4ec9-ae00-dd79c186990c)

### Detection Rule Alert Triggered
![Detection Rule Alert](https://github.com/user-attachments/assets/f68091f9-158a-4312-ae1e-83485287e9b4)

### Kibana Discover (532 Sysmon Events)
![Data Ingestion](https://github.com/user-attachments/assets/76db691b-a817-4d7f-be23-3adb62ebbd1c)

---

## Repository Structure

```
elastic-siem-home-lab/
├── README.md
├── configs/
│   ├── docker-compose.yml
│   └── sysmon-config.xml
├── screenshots/
│   ├── vm-list.png
│   ├── kibana-homepage.png
│   ├── detection-rule-alert.png
│   └── discover-532-events.png
└── notes/
    └── setup-guide.md
```

---

## Skills Demonstrated

**SIEM & Detection Engineering**
- Elasticsearch configuration and management
- Kibana querying and navigation (KQL)
- Detection rule creation and tuning
- Alert threshold optimization
- Log aggregation and analysis

**Endpoint Security**
- Elastic Agent deployment and enrollment
- Sysmon configuration (SwiftOnSecurity baseline)
- Windows Event Log collection
- Endpoint Detection & Response (EDR)

**Infrastructure & Virtualization**
- VirtualBox VM management
- Docker & Docker Compose deployment
- Linux & Windows system administration
- Virtual networking configuration (bridged adapters)

**Security Operations**
- Incident investigation workflows
- Threat hunting and analysis
- MITRE ATT&CK framework mapping
- Attack simulation (Nmap)
- Security event analysis

**Professional**
- Technical documentation and GitHub
- Architecture diagramming
- Portfolio building
- Security operations workflows

---

## Lessons Learned

Building this lab provided hands-on experience troubleshooting:
- Docker networking configuration and container management
- Windows endpoint enrollment in Fleet Server
- Elastic Agent and Sysmon integration
- Detection rule creation and validation
- End-to-end SIEM data pipeline testing

It reinforced practical SOC workflows including log analysis, alert triage, investigation, and incident documentation.

---

## Future Improvements

- [ ] Active Directory Domain Controller
- [ ] Sigma Rules integration
- [ ] Suricata IDS deployment
- [ ] Zeek network monitoring
- [ ] Custom MITRE ATT&CK dashboards
- [ ] Lateral movement simulation
- [ ] Credential access scenarios
- [ ] Threat hunting playbooks

---

## Repository Structure

All lab configurations, documentation, and screenshots are organized in this repository for easy reference and reproduction.

---

## Author

**Somadina Unegbu**

Information Technology Student  
Towson University

Cybersecurity | SOC | Detection Engineering

---

*This lab demonstrates practical SOC skills including SIEM administration, detection engineering, threat hunting, and incident response.*
```

---

