# Detection 02 - PowerShell Process Detection

## Objective

Detect PowerShell execution using Sysmon and Wazuh.

---

## Environment

- Wazuh Manager 4.12
- Ubuntu 24.04
- Windows 10 VM
- Sysmon Installed

---

## Attack Simulation

Executed:

```powershell
powershell.exe -NoProfile -Command "Get-Process"
```

---

## Detection

| Field | Value |
|------|------|
| Rule ID | 92027 |
| Description | Powershell process spawned powershell instance |
| Severity | Level 4 |

---

## MITRE ATT&CK

| Category | Value |
|----------|-------|
| Tactic | Execution |
| Technique | T1059.001 - PowerShell |

---

## Evidence

Image

```
C:\Windows\System32\WindowsPowerShell\v1.0\powershell.exe
```

Command Line

```
powershell.exe -NoProfile -Command Get-Process
```

Parent Process

```
powershell.exe
```

User

```
WINDOWS11\vbxouser
```

---

## Result

Wazuh successfully detected PowerShell execution through Sysmon Event ID 1 (Process Creation). The alert mapped the activity to MITRE ATT&CK technique T1059.001 (PowerShell), demonstrating successful endpoint monitoring and execution detection.
