# SOC Tier 1 Lab Portfolio - Chidozie Nwabiankea

Aspiring SOC Analyst | Lagos, Nigeria | Open to SOC Tier 1 / Intern roles

## Overview
Building hands-on Tier 1 SOC skills through home lab and real alert triage.

## 🛡️ Project 1: Home SOC Lab (Wazuh SIEM)

**Goal:** Detect real attacks on Windows logs

**Setup:**
- Wazuh Manager (Ubuntu VM)
- Windows 10 Agent + Sysmon
- Forwarding Security, Sysmon, PowerShell logs

- ### Lab Setup Steps:
1. **System Hardening First:** Ran `sudo apt update && sudo apt upgrade -y` to patch OS vulnerabilities and update dependencies before SIEM installation. This reduces attack surface and ensures Wazuh dependencies (curl, openssl) are current - standard SOC hardening procedure.
2. Installed Wazuh All-in-One (Manager + Indexer + Dashboard) via official install script
3. Documented each step with screenshots in `/screenshots/wazuh-alerts/`

**Detections Built:**
- [x] Brute-force RDP (4625 multiple failures) -> Alert + MITRE T1110
- [x] Mimikatz/PowerShell suspicious (4104 Script Block) -> Alert + MITRE T1003
- [x] Suspicious process (powershell -> mimikatz) -> Sysmon Event 1 + Event 8

**Screenshots:** /screenshots/wazuh-alerts/
**MITRE Mapping:** T1110, T1003, T1059.1

## 📧 Project 2: Phishing Analysis Playbook

Analyzed 10+ phishing emails using header analysis, URL detonation, IOC extraction.

**Process:**
1. Check SPF/DKIM/DMARC in header
2. Extract URLs + attachments
3. Detonate in Any.Run / VirusTotal
4. Extract IOCs (IP, domain, hash)
5. Write report with Severity + Recommendation

**Template:**
- Sample: [Phish-001]
- Header: From spoofed? Return-Path mismatch?
- IOCs: domain, IP, SHA256
- VT Score: 12/89
- Verdict: Malicious - Credential Harvesting
- MITRE: T1566.002
- Action: Block domain, reset user, awareness

Reports in: /phishing-reports/

## 🚨 Project 3: Incident Triage Reports (LetsDefend)

Completed LetsDefend SOC Alerts - Triaging 15 alerts.

Example:
- Alert: Possible Phishing
- Severity: High
- Analysis: Email with link to fake O365, clicked, creds entered
- IOC: evil-domain.com (VT 15/90)
- MITRE: T1566.002
- Containment: Isolate host, block domain, reset password
- Lesson: User training needed

Full reports: /incident-reports/

## Tools
Wazuh, Sysmon, Wireshark, VirusTotal, Any.Run, MITRE ATT&CK, LetsDefend, TryHackMe SOC L1, Cisco CyberOps

## Certs in Progress
- Cisco CyberOps Associate (200-201 CBROPS) - Studying Security Concepts, Host-Based Analysis, Network Intrusion Analysis
- TryHackMe SOC Level 1 (60% done)
- LetsDefend SOC Analyst Learning Path

## Contact
LinkedIn: linkedin.com/in/nwabiankea-chidozie-9156252a0
Location: Lagos - Remote OK
