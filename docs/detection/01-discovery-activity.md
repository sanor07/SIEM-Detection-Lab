# Detection 01 – Account Discovery

## Objective
Detect account enumeration commands executed on a Windows endpoint.

## Environment

- Wazuh 4.12
- Ubuntu 24.04
- Windows 10 VM
- Sysmon

## Command Executed

net user

## Detection

- Rule ID: 92031
- Rule: Discovery activity executed
- Severity: 3

## MITRE ATT&CK

- Tactic: Discovery
- Technique: T1087 – Account Discovery

## Evidence

Sysmon Event ID 1 captured the execution of `net1.exe`. Wazuh correlated the event with Rule 92031 and identified the activity as account discovery.

## Result

The SIEM successfully detected reconnaissance activity performed on the monitored Windows endpoint.
