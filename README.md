# \# Elastic Stack SIEM Home Lab

# 

# A self-built Security Information and Event Management (SIEM) lab using the Elastic Stack, built to develop hands-on SOC analyst skills: log analysis, detection engineering, and threat simulation mapped to the MITRE ATT\&CK framework.

# 

# \## Goal

# 

# To build hands-on, production-adjacent experience with a real SIEM pipeline — from raw endpoint telemetry to detection, triage, and case documentation — rather than just standing up software with no data flowing through it.

# 

# \## Architecture

# 

# Three virtual machines, networked together to simulate a small enterprise environment:

# 

# | VM | Role | OS | Purpose |

# |---|---|---|---|

# | \*\*elastic-server\*\* | SIEM backend | Ubuntu Server 22.04 (via VirtualBox) | Runs Elasticsearch, Kibana, and Fleet Server — the centralized backend that stores and searches all log data |

# | \*\*endpoint-win\*\* | Monitored endpoint | Windows | Runs Sysmon + Elastic Agent to generate realistic endpoint telemetry (process creation, network connections, registry changes) |

# | \*\*attacker-kali\*\* | Adversary simulation | Kali Linux | Used to generate real attack behavior (via Atomic Red Team, manual technique testing) to validate detection coverage |

# 

# \### Data flow

# 

# \\`\\`\\`

# Sysmon (visibility)

# &#x20;  → Elastic Agent (transport)

# &#x20;  → Fleet Server (management/policy)

# &#x20;  → Elasticsearch (storage, indexed via ECS normalization)

# &#x20;  → Kibana (detection rules, alerts, case management)

# \\`\\`\\`

# 

# \## Tools \& Technologies

# 

# \- \*\*SIEM stack:\*\* Elasticsearch, Kibana, Fleet Server, Elastic Agent (via Docker)

# \- \*\*Endpoint visibility:\*\* Sysmon (SwiftOnSecurity config)

# \- \*\*Attacker tooling:\*\* Kali Linux, Atomic Red Team

# \- \*\*Detection languages:\*\* KQL, EQL

# \- \*\*Framework:\*\* MITRE ATT\&CK

# \- \*\*Hypervisor:\*\* Oracle VirtualBox

# 

# \## Build Summary

# 

# \- \[x] VirtualBox installed, `elastic-server` VM created (Ubuntu Server 22.04, 8GB RAM, 4 vCPU, 60GB disk)

# \- \[x] Network configured in Bridged mode for full connectivity across the lab

# \- \[x] Docker installed on `elastic-server`

# \- \[x] Elastic Stack (Elasticsearch + Kibana + Fleet) deployed via Docker

# \- \[x] Windows endpoint VM built, Sysmon + Elastic Agent installed and enrolled

# \- \[x] Kali attacker VM built

# \- \[x] Prebuilt detection rules enabled in Kibana Security

# \- \[x] Atomic Red Team tests run and mapped to fired alerts

# \- \[x] Custom detection rules written (KQL/EQL)

# \- \[x] Case documentation practice (triage → pivot → ATT\&CK mapping)

# 

# \## SOC Analyst Workflow Practiced

# 

# This lab is built around the core SOC analyst loop:

# 

# 1\. \*\*Triage\*\* — determine if an alert is a true positive, false positive, or benign

# 2\. \*\*Pivot\*\* — investigate surrounding activity (same host, user, timeframe) to build the full picture

# 3\. \*\*Document\*\* — write up findings the way a real SOC ticket/case would be recorded

# 4\. \*\*Map to ATT\&CK\*\* — name the technique (e.g., T1059.001 - PowerShell) rather than describing it vaguely

# 

# \## Notes

# 

# Configs, detection rules, and case write-ups referenced above are included in this repository for reference.

