[wazuh-module-overview-general-1782006916.pdf](https://github.com/user-attachments/files/29169831/wazuh-module-overview-general-1782006916.pdf)  This was my report i got from running Threat Hunter

<img width="1024" height="1536" alt="yes" src="https://github.com/user-attachments/assets/8f8db402-25c0-4d1d-ab0f-98fa0c88ded9" />
# 🛡️ Home SOC Detection Lab

A fully functional Home Security Operations Center (SOC) built using **Wazuh SIEM**, **Sysmon**, and a **Windows 11 endpoint**. This lab demonstrates endpoint monitoring, log collection, process creation visibility, and centralized security analysis.

---

## 📋 Overview

This project simulates a real-world SOC environment where endpoint telemetry is collected, analyzed, and visualized through Wazuh.

The lab consists of:

* Windows 11 Endpoint
* Sysmon for advanced Windows telemetry
* Wazuh Agent
* Wazuh Manager
* Wazuh Dashboard
* VirtualBox virtualization

The goal was to gain hands-on experience with SIEM deployment, endpoint monitoring, and threat detection fundamentals.

---

## 🏗️ Architecture

```text
Windows Endpoint
(Wazuh Agent + Sysmon)
          │
          ▼
     Wazuh Manager
          │
          ▼
    Wazuh Dashboard
```

---

## 🔧 Technologies Used

| Technology | Purpose                          |
| ---------- | -------------------------------- |
| Wazuh 4.12 | SIEM, log collection, monitoring |
| Sysmon v15 | Advanced Windows telemetry       |
| Windows 11 | Endpoint monitoring              |
| VirtualBox | Virtualization platform          |
| Linux      | Wazuh server deployment          |

---

## 🎯 Lab Objectives

* Deploy a Wazuh SIEM environment
* Configure a Windows endpoint
* Install and configure Sysmon
* Connect endpoint telemetry to Wazuh
* Monitor process creation events
* Validate Sysmon log ingestion
* Build a foundation for threat detection and hunting

---

## 🚀 Setup Process

### 1. Deploy Wazuh

* Imported Wazuh OVA
* Configured networking
* Verified dashboard access

### 2. Install Windows Endpoint

* Created Windows 11 VM
* Configured network connectivity
* Verified communication with Wazuh Manager

### 3. Install Wazuh Agent

* Downloaded and installed the Windows agent
* Registered endpoint with the Wazuh Manager
* Verified successful enrollment

### 4. Install Sysmon

Installed Sysmon using SwiftOnSecurity's Sysmon configuration.

```powershell
Sysmon.exe -accepteula -i sysmonconfig-export.xml
```

Verified successful installation by reviewing Sysmon operational logs.

### 5. Configure Wazuh for Sysmon

Added the following configuration to `ossec.conf`:

```xml
<localfile>
  <location>Microsoft-Windows-Sysmon/Operational</location>
  <log_format>eventchannel</log_format>
</localfile>
```

Restarted the Wazuh agent service and confirmed log collection.

---

## 📊 Results

### Wazuh Dashboard

* 1 Active Agent
* Windows endpoint successfully connected
* Alerts and telemetry visible in dashboard

### Event Collection

Successfully collected and visualized:

* Windows Event Logs
* Sysmon Operational Logs
* Process Creation Events
* Endpoint Security Events

### Sysmon Verification

Verified ingestion of:

```text
data.win.system.channel = Microsoft-Windows-Sysmon/Operational
```

### Process Creation Monitoring

Verified Sysmon Event ID:

```text
Event ID 1
```

Used to monitor:

* Process launches
* Command execution
* Parent-child process relationships

---

## 🔍 Example Queries

### Sysmon Events

```text
data.win.system.channel:"Microsoft-Windows-Sysmon/Operational"
```

### Process Creation Events

```text
data.win.system.eventID:1
```

### Endpoint Events

```text
agent.name:"Windows-Endpoint"
```

---

## 📸 Screenshots

### Dashboard Overview

Shows connected endpoint and overall security monitoring status.

### Event Collection

Demonstrates successful collection of Windows telemetry.

### Process Creation Events

Displays Sysmon Event ID 1 process creation visibility.

### Sysmon Operational Channel

Confirms successful Sysmon integration with Wazuh.

---

## 🧠 Skills Demonstrated

* SIEM Deployment
* Security Monitoring
* Endpoint Telemetry Collection
* Windows Event Logging
* Sysmon Configuration
* Wazuh Administration
* Log Analysis
* Threat Hunting Fundamentals
* Security Operations

---

## 📚 Lessons Learned

Throughout this project I gained hands-on experience with:

* Deploying and managing Wazuh
* Configuring Sysmon for advanced visibility
* Troubleshooting agent enrollment issues
* Understanding Windows Event Channels
* Creating a centralized monitoring environment
* Investigating endpoint telemetry

---

## 🔮 Future Improvements

* Custom Wazuh Detection Rules
* MITRE ATT&CK Mapping
* Sigma Rule Integration
* PowerShell Detection
* Mimikatz Detection
* Threat Intelligence Integration
* Multi-endpoint Environment
* Active Response Automation
* Detection Engineering Projects

---

## 📌 Project Status

✅ Wazuh Operational

✅ Windows Agent Connected

✅ Sysmon Installed

✅ Sysmon Logs Collected

✅ Process Creation Monitoring Active

✅ Home SOC Operational

