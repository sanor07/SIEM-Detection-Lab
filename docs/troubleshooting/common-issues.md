# Common Issues

## Agent Disconnected

Symptoms

- Agent offline
- Dashboard unavailable

Solution

- Verify Manager IP
- Restart Wazuh Agent
- Verify connectivity on port 1514

---

## Dashboard Unreachable

Symptoms

ERR_CONNECTION_TIMED_OUT

Solution

hostname -I

Update browser URL with new IP.

---

## Registry Detection Missing

Problem

Sysmon generated Event ID 13 but Wazuh did not generate alerts.

Status

Under investigation.
