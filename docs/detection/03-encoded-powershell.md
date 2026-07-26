# Detection 03 – Base64 Encoded PowerShell Detection

## Overview

This detection demonstrates how Wazuh and Sysmon identify PowerShell processes executing Base64-encoded commands. Attackers frequently use Base64 encoding to obfuscate PowerShell commands and evade basic detection mechanisms.

---

## Objective

- Simulate encoded PowerShell execution.
- Verify Sysmon Event ID 1 logging.
- Validate Wazuh detection.
- Map the activity to MITRE ATT&CK.

---

## Lab Environment

| Component | Value |
|-----------|-------|
| SIEM | Wazuh 4.12 |
| Manager | Ubuntu 24.04 |
| Endpoint | Windows 10 VM |
| Monitoring | Sysmon |

---

## Attack Simulation

Generate a Base64 encoded command.

```powershell
$command='Get-Process'
$bytes=[System.Text.Encoding]::Unicode.GetBytes($command)
$encoded=[Convert]::ToBase64String($bytes)
$encoded
```

Execute:

```powershell
powershell.exe -EncodedCommand <Base64_String>
```

---

## Detection Details

| Field | Value |
|-------|-------|
| Rule ID | 92057 |
| Severity | 12 |
| Event Source | Sysmon Event ID 1 |
| Description | PowerShell.exe spawned a PowerShell process which executed a Base64 encoded command |

---

## MITRE ATT&CK

| Category | Value |
|----------|-------|
| Tactic | Execution |
| Technique | T1059.001 |
| Name | PowerShell |

---

## Evidence

Executable

```
C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe
```

Command Line

```
powershell.exe -EncodedCommand <Base64_String>
```

Parent Process

```
powershell.exe
```

User

```
WINDOWS\vbxouser
```

---

## Screenshots

### Detection Alert

![Alert](../../screenshots/detection/03-encoded-powershell-alert.png)

### Event Details

![Details](../../screenshots/detection/03-encoded-powershell-details.png)

---

## Analysis

PowerShell supports the `-EncodedCommand` parameter, allowing commands to be executed using Base64 encoding. This technique is frequently observed in malware and red-team activities because it hides the original command from casual inspection.

Sysmon recorded the process creation event and Wazuh correlated it with Rule 92057, correctly identifying the execution of an encoded PowerShell command.

---

## Learning Outcomes

- Encoded PowerShell execution
- Sysmon Event ID 1 analysis
- Wazuh rule correlation
- MITRE ATT&CK mapping
- Threat hunting
- Security event analysis

---

## Result

The encoded PowerShell command was successfully detected by Wazuh using Sysmon telemetry and mapped to MITRE ATT&CK Technique T1059.001.
