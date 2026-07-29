# Detection 05 - User Account Discovery

## Objective

Detect account enumeration activity on a Windows endpoint using Sysmon and Wazuh.

---

## MITRE ATT&CK

| Field | Value |
|-------|-------|
| Tactic | Discovery |
| Technique | T1087 - Account Discovery |

---

## Environment

- Wazuh 4.12
- Ubuntu 24.04 (Manager)
- Windows 10 VM (Agent)
- Sysmon

---

## Attack Simulation

Executed the following Windows discovery commands:

```cmd
whoami
net user
query user
whoami /groups
net localgroup administrators
