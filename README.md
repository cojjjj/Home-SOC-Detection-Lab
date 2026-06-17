# 🛡️ Home SOC Detection Lab

A home Security Operations Center (SOC) lab built using Wazuh, Sysmon, Windows Event Logs, and custom detection rules to simulate real-world security monitoring and incident response workflows.

---

## 🎯 Project Goals

- Deploy a SIEM platform
- Collect and analyze security logs
- Create custom detection rules
- Simulate attacker techniques
- Investigate alerts
- Document incident response procedures
- Map detections to MITRE ATT&CK

---

## 🏗️ Lab Architecture

```text
Windows Endpoint
       │
       ▼
   Sysmon
       │
       ▼
 Wazuh Agent
       │
       ▼
 Wazuh Manager
       │
       ▼
 Alerts & Dashboards
```

---

## 🔍 Detection Use Cases

- Suspicious PowerShell Activity
- Failed Login Brute Force Attempts
- New Local Administrator Creation
- Persistence Mechanisms
- Credential Dumping Activity
- Unauthorized Process Execution

---

## 🛠️ Tools Used

- Wazuh
- Sysmon
- Windows Event Logs
- Sigma Rules
- Ubuntu Server
- VirtualBox
- PowerShell
- MITRE ATT&CK Framework

---

## 📂 Repository Structure

```text
architecture/
attack-simulations/
detections/
incident-reports/
screenshots/
setup/
```

---

## 📈 Skills Demonstrated

- SIEM Deployment
- Detection Engineering
- Threat Hunting
- Log Analysis
- Incident Response
- Windows Security Monitoring
- SOC Operations

---

## 🚧 Project Status

Currently building the lab environment and implementing detection rules.
