# Wazuh Home SOC Lab (Beginner Project)

## Overview
This project documents my beginner Security Operations Center (SOC) lab built using **Wazuh SIEM** on **Kali Linux** and a **Windows 10** endpoint inside VirtualBox. The goal was to practice SIEM deployment, endpoint onboarding, alert triage, and basic incident reporting.

## Lab Setup
**Environment**
- Host: Windows 11 (VirtualBox)
- SIEM Server: Kali Linux (Wazuh Manager + Indexer + Dashboard)
- Endpoint: Windows 10 (Wazuh Agent)

**Network**
- VirtualBox NAT Network
- Wazuh Dashboard: `https://10.0.2.15`

## What I Did
- Installed Wazuh all-in-one deployment on Kali Linux
- Enrolled Windows 10 endpoint as an agent
- Verified log ingestion and agent health
- Generated and investigated security events (authentication failures)

## Detection Scenario: Failed Login Attempts
**Goal:** Detect repeated failed logins and investigate details in the SIEM.

- Windows Event ID: **4625** (failed login)
- Alert level: **5 (Medium)**
- Example investigation fields:
  - Target username
  - Source IP address
  - Number of attempts
  - Rule description

## Evidence (Screenshots)
Add screenshots in a folder like:
- `screenshots/agents-active.png`
- `screenshots/failed-logins-4625.png`

## Incident Report
A short incident report is included in:
- `incident-report/incident-report.md`

## Skills Demonstrated
- SIEM deployment (Wazuh)
- Endpoint onboarding and troubleshooting
- Log filtering and investigation
- Alert triage and basic incident reporting

## Next Improvements
- Add Sysmon for richer Windows telemetry
- Create custom detection rules
- Add dashboards for authentication monitoring
- Map detections to MITRE ATT&CK
- ## MITRE ATT&CK Mapping

The failed login activity maps to:

- Technique: T1110 – Brute Force
- Tactic: Credential Access

Although the test activity originated locally, similar behavior from a remote IP would indicate potential brute-force attempts.
