# 🎨 Assets

This directory contains all branding resources, diagrams, and visual assets used throughout the **SIEM Detection Engineering Lab** project.

These assets are used in the main documentation, GitHub README, presentations, and future project documentation.

---

# 📂 Directory Structure

```text
assets/
│
├── banner.png
├── logo.png
├── architecture.drawio
├── architecture.png
├── favicon.png
└── wordmark.png
```

---

# 📁 Asset Description

| File | Description |
|------|-------------|
| **banner.png** | Official GitHub repository banner displayed at the top of the README. |
| **logo.png** | Primary project logo representing the SIEM Detection Engineering Lab. |
| **architecture.drawio** | Editable Draw.io source file for the system architecture diagram. |
| **architecture.png** | Exported architecture diagram used in project documentation. |
| **favicon.png** | Simplified project icon for websites and browser tabs. *(Optional)* |
| **wordmark.png** | Horizontal project logo for documentation and presentations. *(Optional)* |

---

# 🖥️ Branding Guidelines

The visual identity of this project follows a modern enterprise cybersecurity theme inspired by professional Security Operations Center (SOC) platforms.

## Design Language

- Dark cybersecurity theme
- Blue & cyan accent colors
- Glassmorphism UI
- Enterprise documentation style
- Microsoft Azure inspired layouts
- Elastic Security inspired dashboards
- Cisco architecture styling

---

# 🎯 Logo Concept

The project logo represents the core concepts of Detection Engineering.

| Element | Meaning |
|---------|----------|
| 🛡 Shield | Defense & Security |
| 🔍 Magnifying Glass | Threat Hunting |
| ✔ Check Mark | Successful Detection |
| 🔵 Circuit Lines | Detection Engineering |
| 🌐 Hexagonal Pattern | Network Infrastructure |
| 📡 Radar Sweep | Continuous Monitoring |

---

# 🏗️ Architecture Diagram

The architecture diagram illustrates the complete event processing workflow.

```
Windows Endpoint
        │
        ▼
Sysmon
        │
        ▼
Windows Event Logs
        │
        ▼
Wazuh Agent
        │
        ▼
Ubuntu SIEM Server
        ├── Filebeat
        ├── Wazuh Manager
        ├── Wazuh Indexer
        └── Wazuh Dashboard
        │
        ▼
SOC Analyst
```

---

# 🎨 Color Palette

| Color | Purpose |
|--------|----------|
| 🔵 Blue | Monitoring |
| 🟢 Green | Detection |
| 🟠 Orange | Investigation |
| 🟣 Purple | Threat Hunting |
| ⚫ Dark Navy | Background |

---

# 📝 Notes

- All diagrams are created using **draw.io**.
- PNG files are exported from their corresponding `.drawio` source files.
- Branding assets are optimized for GitHub, documentation, and presentations.
- Future diagrams will follow the same design language for consistency.

---

# 📌 Future Assets

The following assets will be added as the project evolves:

- Detection Pipeline Diagram
- MITRE ATT&CK Coverage Diagram
- Detection Lifecycle Diagram
- Threat Hunting Workflow
- Incident Response Flow
- Active Response Architecture
- Sigma Rule Workflow

---

**Maintained by:** Sanowar Hussain
