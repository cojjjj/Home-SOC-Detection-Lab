# 🛡️ Home SOC Detection Lab

## Overview

A Home Security Operations Center (SOC) built using Wazuh SIEM, Sysmon, and a Windows 11 endpoint. This lab demonstrates endpoint monitoring, centralized log collection, and process creation visibility through Sysmon telemetry.

## Architecture

```text
Windows Endpoint (Sysmon + Wazuh Agent)
            │
            ▼
      Wazuh Manager
            │
            ▼
     Wazuh Dashboard
```

## Technologies Used

* Wazuh 4.12
* Sysmon v15
* Windows 11
* VirtualBox
* Linux

## Lab Objectives

* Deploy Wazuh
* Install a Windows endpoint
* Configure Sysmon
* Collect Sysmon logs
* Monitor process creation events
* Perform threat hunting

## Verification

### Sysmon Events

```text
data.win.system.channel:"Microsoft-Windows-Sysmon/Operational"
```

### Process Creation Events

```text
data.win.system.eventID:1
```

## Results

* Wazuh agent successfully enrolled
* Sysmon operational logs collected
* Process creation monitoring active
* Endpoint telemetry visible in Wazuh

## Future Improvements

* Custom detection rules
* Sigma integration
* PowerShell detections
* MITRE ATT&CK mapping
* Multi-endpoint monitoring

