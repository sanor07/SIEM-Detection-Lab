# Wazuh Installation Guide

## Environment

| Component | Version |
|-----------|---------|
| Host OS | Windows 11 |
| Hypervisor | Oracle VirtualBox |
| SIEM Server | Ubuntu 24.04 LTS |
| Wazuh | 4.12 |
| Endpoint | Windows 11 |
| Log Source | Sysmon |

---

## Prerequisites

- Oracle VirtualBox installed
- Ubuntu 24.04 LTS virtual machine
- Internet connection
- Minimum 4 CPU cores
- Minimum 8 GB RAM
- Minimum 80 GB storage

---

## Installation Steps

### 1. Create Ubuntu Virtual Machine

- Install Ubuntu 24.04 LTS
- Update the system

### 2. Install Guest Additions

- Enable shared clipboard
- Enable dynamic display resizing

### 3. Configure Networking

- Configure VirtualBox networking
- Verify internet connectivity

### 4. Install Wazuh

Install the Wazuh All-in-One server.

> Installation screenshots will be added after deployment is complete.

---

## Next Steps

- Install Wazuh Agent
- Install Sysmon
- Verify agent connection
- Generate security events
- Investigate alerts
