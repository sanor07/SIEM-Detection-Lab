# Detection Rules

## Overview

This document explains how Wazuh detects security events in the SIEM Detection Lab.

---

## Detection Sources

- Sysmon Logs
- Windows Event Logs
- File Integrity Monitoring (FIM)
- Authentication Events
- Process Creation Events
- Network Events

---

## Planned Custom Rules

- Port Scan Detection
- Brute Force Detection
- PowerShell Detection
- Suspicious Process Detection
- Registry Modification Detection
- File Integrity Monitoring Alerts

---

## Future Improvements

As the project progresses, this document will include:

- Custom Wazuh Rules
- Local Decoders
- Alert Levels
- Rule Testing
- MITRE ATT&CK Mapping
- Detection Screenshots



## Project Progress

| Detection | MITRE ATT&CK | Rule ID | Status |
|-----------|--------------|---------|--------|
| Detection 01 - Account Discovery | T1087 | 92031 | ✅ Completed |
| Detection 02 - PowerShell Execution | T1059.001 | 92027 | ✅ Completed |
| Detection 03 - Base64 Encoded PowerShell | T1059.001 | 92057 | ✅ Completed |
| Detection 04 - High Severity Alert Investigation | Rule 92213 | Pending | ⏳ |
| Detection 05 - Persistence Techniques | T1547 | Planned | ⏳ |
| Detection 06 - File Integrity Monitoring | T1070 | Planned | ⏳ |
| Detection 07 - Brute Force Detection | T1110 | Planned | ⏳ |
| Detection 08 - Custom Wazuh Rules | Custom | Planned | ⏳ |
| Detection 09 - SOC Incident Report | Multiple | Planned | ⏳ |
