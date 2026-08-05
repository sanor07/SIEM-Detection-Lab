# Detection 06 - PowerShell Download Cradle (Research)

## Objective

Investigate how to detect PowerShell download cradle activity using Wazuh, Sysmon, and custom detection rules.

---

## MITRE ATT&CK

| Tactic | Technique | ID |
|---------|-----------|----|
| Command and Control | Ingress Tool Transfer | T1105 |
| Execution | PowerShell | T1059.001 |

---

## Lab Environment

- Windows 10 VM
- Sysmon
- Wazuh Agent
- Ubuntu 24.04 Server
- Wazuh Manager 4.12
- Wazuh Dashboard

---

## Attack Simulation

Executed the following PowerShell command:

```powershell
Invoke-WebRequest -Uri "https://example.com" -OutFile "$env:TEMP\example.html"
```

---

## Verification

### Windows Sysmon

Verified that Sysmon Event ID 1 successfully logged the PowerShell execution.

Evidence included:

- Image: `powershell.exe`
- CommandLine:
  ```
  Invoke-WebRequest https://example.com
  ```
- Event ID: 1 (Process Create)

---

### Wazuh

Verified that:

- Wazuh Manager was operational.
- Wazuh Dashboard was operational.
- Sysmon Event ID 1 telemetry was being received.
- Existing Sysmon detections were functioning correctly.

---

## Custom Rule Development

Created a custom Wazuh rule intended to detect PowerShell download cradle activity.

Example detection target:

- Invoke-WebRequest
- iwr
- curl
- wget

Rule ID:

```
100101
```

---

## Current Status

The custom detection is currently under investigation.

Windows Sysmon successfully records the PowerShell activity; however, the specific PowerShell Event ID 1 has not yet been observed inside Wazuh alerts.

Current evidence suggests additional investigation is required into:

- Windows EventChannel collection
- Wazuh Agent telemetry
- Sysmon Event forwarding
- Custom rule matching

---

## Skills Practiced

- Detection Engineering
- Sysmon Event Analysis
- Wazuh Rule Development
- Event Validation
- Threat Hunting
- MITRE ATT&CK Mapping
- Detection Troubleshooting

---

## Lessons Learned

- Always validate telemetry before developing detection logic.
- Verify Windows event collection prior to writing custom rules.
- Use Sysmon to confirm local event generation.
- Use Wazuh to verify event ingestion before rule testing.
- Detection engineering requires validating each stage of the telemetry pipeline.

---

## Future Work

- Resolve Windows EventChannel forwarding.
- Complete custom PowerShell download cradle detection.
- Validate Rule ID 100101.
- Generate detection alerts inside Wazuh Dashboard.
- Extend the rule to detect additional download utilities.

---

## References

- Wazuh Documentation
- Sysmon Documentation
- MITRE ATT&CK T1059.001
- MITRE ATT&CK T1105
