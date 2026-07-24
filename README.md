# SIEM Detection Lab

A hands-on Security Information and Event Management (SIEM) lab built using **Wazuh**, **Ubuntu 24.04 LTS**, **Windows 11**, **Sysmon**, and **Oracle VirtualBox**.

This project demonstrates how to deploy a complete SIEM environment, collect endpoint telemetry, detect security events, and investigate attacks in a controlled virtual lab.

---

# Project Objectives

- Deploy a complete Wazuh SIEM environment.
- Monitor Windows endpoints using Sysmon.
- Collect and analyze security logs.
- Simulate cyber attacks.
- Create custom detection rules.
- Investigate alerts through the Wazuh Dashboard.
- Map detections to the MITRE ATT&CK Framework.

# Features

- Wazuh SIEM Deployment
- Ubuntu 24.04 Server
- Windows 11 Endpoint
- Sysmon Integration
- Log Collection
- Security Monitoring
- Alert Investigation
- Attack Simulation
- MITRE ATT&CK Mapping

# Technology Stack

| Component | Technology |
|-----------|------------|
| SIEM | Wazuh 4.12 |
| Operating System | Ubuntu 24.04 LTS |
| Endpoint | Windows 11 |
| Log Collection | Sysmon |
| Virtualization | Oracle VirtualBox |
| Version Control | Git |
| Repository | GitHub |

# Lab Architecture

The SIEM Detection Lab consists of the following components:

- **Ubuntu 24.04 LTS** running Wazuh Manager, Wazuh Indexer, and Wazuh Dashboard.
- **Windows 11** endpoint monitored by the Wazuh Agent.
- **Sysmon** for advanced Windows event logging.
- **Oracle VirtualBox** for virtualization.
- **GitHub** for project documentation and version control.

> A detailed architecture diagram will be added after the deployment is complete.

# Repository Structure

```text
SIEM-Detection-Lab/
│
├── assets/
├── configs/
├── docs/
├── logs/
├── screenshots/
├── scripts/
├── README.md
├── LICENSE
└── .gitignore
```
# Project Progress

- [x] Ubuntu 24.04 Installation
- [x] VirtualBox Configuration
- [x] Guest Additions
- [x] SSH Configuration
- [ ] Wazuh Installation
- [ ] Windows Agent Deployment
- [ ] Sysmon Installation
- [ ] Attack Simulation
- [ ] Custom Detection Rules
- [ ] Dashboard Analysis
