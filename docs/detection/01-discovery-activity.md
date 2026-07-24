# Detection 01 - Discovery Activity Executed

## Objective
Detect Windows discovery commands using Sysmon Event ID 1.

## Environment

- Ubuntu 24.04
- Wazuh 4.12
- Windows 10 VM
- Sysmon

## Commands Executed

whoami
hostname
systeminfo
ipconfig
tasklist
net user

## Detection

Wazuh triggered Rule 92031 (Discovery activity executed).

Rule File:
0800-sysmon_id_1.xml

Severity:
Level 3

## MITRE ATT&CK

- TA0007 - Discovery
- T1082 - System Information Discovery

## Result

The SIEM successfully detected reconnaissance commands executed on the monitored Windows endpoint.
