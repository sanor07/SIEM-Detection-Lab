# Detection 03 – Base64 Encoded PowerShell Detection

## Overview

This detection demonstrates how Wazuh and Sysmon identify PowerShell processes executing Base64-encoded commands. Attackers frequently use encoded PowerShell commands to obfuscate malicious scripts and evade simple detection mechanisms.

This activity was successfully detected by Wazuh and mapped to the MITRE ATT&CK framework.

---

## Objective

- Simulate an attacker executing an encoded PowerShell command.
- Verify Sysmon captures the process creation event.
- Confirm Wazuh generates the appropriate security alert.
- Analyze the event and map it to MITRE ATT&CK.

---

## Lab Environment

| Component | Value |
|----------|-------|
| SIEM | Wazuh 4.12 |
| Operating System | Ubuntu 24.04 LTS |
| Endpoint | Windows 10 VM |
| Monitoring Tool | Sysmon |
| Event Source | Microsoft-Windows-Sysmon |

---

## Attack Simulation

### Step 1: Generate a Base64 Encoded Command

```powershell
$command = 'Get-Process'
$bytes = [System.Text.Encoding]::Unicode.GetBytes($command)
$encoded = [Convert]::ToBase64String($bytes)
$encoded
```

### Step 2: Execute the Encoded Command

```powershell
powershell.exe -EncodedCommand <Base64_String>
```

Example:

```powershell
powershell.exe -EncodedCommand RwBlAHQALQBQAHIAbwBjAGUAcwBzAA==
```

---

## Detection

Wazuh generated the following alert after the encoded PowerShell command was executed.

| Field | Value |
|------|------|
| Rule ID | 92057 |
| Severity | 12 |
| Description | PowerShell.exe spawned a PowerShell process which executed a Base64 encoded command |
| Decoder | windows_eventchannel |
| Source | Microsoft-Windows-Sysmon |

---

## MITRE ATT&CK Mapping

| Category | Value |
|----------|-------|
| Tactic | Execution |
| Technique | T1059.001 |
| Technique Name | PowerShell |

---

## Evidence

### Process Image

```
C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe
```

### Command Line

```powershell
powershell.exe -EncodedCommand <Base64_String>
```

### Parent Process

```
powershell.exe
```

### User

```
WINDOWS11\vbxouser
```

---

## Screenshots

### Alert Overview

![Encoded PowerShell Alert](../../screenshots/detection/03-encoded-powershell-alert.png)

### Event Details

![Encoded PowerShell Details](../../screenshots/detection/03-encoded-powershell-details.png)

---

## Security Analysis

PowerShell supports executing commands that are encoded using Base64 through the `-EncodedCommand` parameter. This technique is widely used by attackers because it obscures the original command, making it more difficult to identify through basic command-line inspection.

Sysmon captured the process creation event and forwarded it to the Wazuh Manager. Wazuh correlated the event with its detection rules and generated **Rule 92057**, identifying the execution of a Base64-encoded PowerShell command.

This behavior aligns with **MITRE ATT&CK Technique T1059.001 (PowerShell)** under the **Execution** tactic.

---

## Learning Outcomes

- Generated Base64-encoded PowerShell commands.
- Simulated attacker command obfuscation.
- Verified Sysmon Event ID 1 process creation logging.
- Validated Wazuh detection capabilities.
- Performed MITRE ATT&CK mapping.
- Collected forensic evidence for security analysis.

---

## Result

The simulated encoded PowerShell execution was successfully detected by Wazuh. Sysmon recorded the process creation event, and Wazuh generated **Rule 92057 (Severity Level 12)**, correctly identifying the use of a Base64-encoded PowerShell command. This confirms that the SIEM environment can detect common attacker techniques involving PowerShell command obfuscation.
