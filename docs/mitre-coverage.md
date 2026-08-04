# MITRE ATT&CK Coverage

This document maps the detections implemented in this SIEM Detection Engineering Lab to the MITRE ATT&CK Framework.

---

# Coverage Summary

| MITRE ID | Technique | Tactic | Detection | Status |
|----------|-----------|--------|-----------|--------|
| T1087 | Account Discovery | Discovery | User Account Discovery | ✅ |
| T1059.001 | PowerShell | Execution | PowerShell Execution Detection | ✅ |
| T1027 | Obfuscated / Encoded Files or Information | Defense Evasion | Encoded PowerShell Detection | ✅ |
| T1105 | Ingress Tool Transfer | Command and Control | High Severity Investigation | ✅ |
| T1570 | Lateral Tool Transfer | Lateral Movement | Executable File Creation Detection | ✅ |
| T1105 | PowerShell Download Cradle | Command and Control | Planned Detection | ✅ |

---

# Technique Details

## T1087 - Account Discovery

**Tactic**

Discovery

### Description

Attackers enumerate local or domain user accounts to understand the environment before privilege escalation or lateral movement.

### Detection

- Monitor execution of:
  - net user
  - net localgroup
  - whoami
  - query user

### Detection Status

✅ Implemented

---

## T1059.001 - PowerShell

**Tactic**

Execution

### Description

PowerShell is frequently abused by attackers to execute commands, download payloads, and automate malicious activity.

### Detection

- PowerShell process creation
- Command-line monitoring
- Sysmon Event ID 1

### Detection Status

✅ Implemented

---

## T1027 - Obfuscated / Encoded Files or Information

**Tactic**

Defense Evasion

### Description

Attackers use Base64 encoding and obfuscation techniques to bypass traditional security controls.

### Detection

- EncodedCommand
- Base64 strings
- Suspicious PowerShell parameters

### Detection Status

✅ Implemented

---

## T1105 - Ingress Tool Transfer

**Tactic**

Command and Control

### Description

Adversaries download additional tools or payloads onto compromised systems.

### Detection

- High severity executable download investigation
- PowerShell Download Cradle (Planned)

### Detection Status

🚧 In Progress

---

## T1570 - Lateral Tool Transfer

**Tactic**

Lateral Movement

### Description

Executable files are copied between systems to facilitate lateral movement.

### Detection

- Sysmon Event ID 11
- Executable file creation
- DLL monitoring

### Detection Status

✅ Implemented

---

# MITRE Coverage Statistics

| Metric | Value |
|---------|------:|
| Techniques Covered | 5 |
| Tactics Covered | 5 |
| Completed Detections | 6 |
| Planned Detections | 1 |

---

# Future Coverage

The project will continue expanding to include:

- Credential Dumping (T1003)
- Registry Persistence (T1547.001)
- Scheduled Tasks (T1053)
- RDP Abuse (T1021.001)
- Process Injection (T1055)
- Service Creation (T1543)
- Remote Command Execution
- Persistence via Startup Folder
- DLL Search Order Hijacking
- WMI Persistence

---

# References

- MITRE ATT&CK Framework
- Wazuh Documentation
- Sysmon Documentation
