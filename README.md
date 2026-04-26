# Endpoint Automation Platform (WIP / Concept)

![Architecture Diagram](https://github.com/William112792/autopilot-deployment-lab/blob/main/diagrams/UnrealEngine_Architecture_AutopilotSimulator.png?raw=true)

## Overview

The **Endpoint Automation Platform** is a simulated environment designed to demonstrate modern endpoint management and automation practices, focusing on:

* Zero-Touch Provisioning (Windows Autopilot)
* Microsoft Intune Administration
* Endpoint Configuration & Compliance
* Application Deployment
* Remediation Automation
* Remote Device Management (vPro EMA Simulation)

This project provides a **hands-on, interactive lab experience** using a combination of:

* Unreal Engine (UI simulation layer)
* SQLite (data persistence layer)
* Structured automation logic inspired by real-world enterprise environments

The goal is to **bridge the gap between theory and execution** by allowing users to simulate enterprise-grade endpoint workflows without requiring a live tenant.

---

## Key Features

### 1. Vendor / Procurement Simulation

* Select device manufacturer and model
* Auto-generate serial numbers based on defined patterns
* Assign Group Tags (optional)
* Prevent duplicate Group Tag creation
* Simulate device ordering workflows

---

### 2. Microsoft Intune Admin Center (Simulated)

A layered UI system replicating real-world Intune navigation:

#### Top-Level Navigation

* Devices
* Apps
* Users
* Groups

#### Core Capabilities

* Device enrollment tracking
* Group Tag assignment
* Application targeting
* Remediation script association
* Device reset and lifecycle management

---

### 3. Remote Management (vPro EMA Simulation)

* Select device by name
* Power on device remotely
* Trigger enrollment workflow
* Simulate:

  * Device Preparation
  * Account Setup
  * Policy & App Deployment
* Persist enrollment state
* Reset device from Intune simulation

---

## Architecture Overview

```
[ Unreal Engine UI Layer ]
        ↓
[ Widget Switchers / UI Logic ]
        ↓
[ SQLite3 Database ]
        ↓
[ Data Models ]
    ├── Devices
    ├── Device Models
    ├── Manufacturers
    ├── Group Tags
    ├── Apps
    ├── Remediation Scripts
    ├── Users / Groups
    └── Device-App Relationships
```

All UI interactions execute **SQL queries** to simulate real backend behavior.

---

## Database Design (Core Tables)

| Table              | Purpose                             |
| ------------------ | ----------------------------------- |
| Manufacturers      | Device vendors                      |
| DeviceModels       | Model definitions + serial patterns |
| Devices            | Unique device records               |
| GroupTags          | Logical device grouping             |
| DeviceGroupTag     | Mapping devices to tags             |
| Apps               | Application catalog                 |
| DeviceApps         | Deployment relationships            |
| RemediationScripts | Script automation logic             |
| Users / Groups     | Identity simulation                 |

---

## How It Works

1. **Procurement Layer**

   * Create a device with manufacturer + model
   * Assign optional Group Tag

2. **Intune Simulation**

   * Configure apps, scripts, and group targeting
   * Associate configurations with Group Tags

3. **Remote Management**

   * Power on device
   * Trigger Autopilot-like enrollment
   * Apply configurations dynamically

4. **State Persistence**

   * Enrollment status saved in SQLite
   * Future boots skip enrollment unless reset

---

## Technologies Used

* **Unreal Engine**

  * Widget Switchers for UI simulation
  * State-driven navigation
* **SQLite3**

  * Lightweight relational database
  * Local persistence for all objects
* **PowerShell (Future Integration)**

  * Remediation script modeling
* **Microsoft Intune Concepts**

  * Device lifecycle modeling
  * Policy + app deployment logic

---

## Use Cases

* Demonstrate endpoint automation skills in a portfolio
* Train new engineers on Intune concepts without tenant access
* Prototype automation workflows before production rollout
* Visualize device lifecycle and policy impact

---

## Related Repositories

* Autopilot Deployment Lab
  https://github.com/William112792/autopilot-deployment-lab

* Intune Remediation Scripts
  https://github.com/William112792/intune-remediation-scripts

---

## Future Enhancements

* Primary User assignment logic
* Compliance policy simulation
* Conditional Access modeling
* Reporting dashboards
* Multi-tenant simulation
* API integration layer (Graph simulation)

---

## Why This Matters

Modern endpoint management is increasingly driven by **automation, APIs, and declarative configuration** rather than manual processes. Platforms like GitHub emphasize automation for managing workflows, infrastructure, and deployments at scale. ([The GitHub Blog][1])

This project demonstrates:

* Practical understanding of endpoint lifecycle automation
* Ability to model enterprise systems
* Skills in UI simulation, state management, and data modeling
* Forward-thinking approach to training and tooling

---

## Getting Started (Planned)

```bash
# Clone repository
git clone https://github.com/William112792/endpoint-automation-platform

# Open Unreal Engine project
# Configure SQLite database
# Launch simulation
```

---

## Contribution

Contributions are welcome:

* New UI modules
* Additional automation scenarios
* Expanded database models
* Script integrations

---

## License

MIT License

---

## Author

# 👤 Author

Billy Gordon  
Endpoint Automation Engineer  
Intune | PowerShell | Automation

[1]: https://github.blog/enterprise-software/automation/?utm_source=chatgpt.com "The latest on automation - The GitHub Blog"
