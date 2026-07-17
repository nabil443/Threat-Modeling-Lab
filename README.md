# 🛡️ Security Monitoring Lab (SOC Lab)

## 📌 Overview

This repository contains my Security Operations Center (SOC) laboratory exercises completed using Ubuntu Server, Wazuh SIEM, Wazuh Agent, and VirusTotal Threat Intelligence Integration.

The purpose of this project is to demonstrate the complete deployment of a security monitoring environment capable of collecting endpoint events, monitoring file integrity, integrating external threat intelligence, and generating real-time security alerts.

---

# 🎯 Objectives

- Install and configure Ubuntu Server
- Install and configure Wazuh Manager
- Add and manage Wazuh Agents
- Configure File Integrity Monitoring (FIM)
- Integrate VirusTotal with Wazuh
- Generate security alerts
- Monitor alerts from the Wazuh Dashboard

---

# 🏗️ Lab Architecture

```
                 +---------------------+
                 |   Ubuntu Server     |
                 |  Wazuh Manager      |
                 +----------+----------+
                            |
                Agent Communication
                            |
         +------------------+------------------+
         |                                     |
+------------------+                 +------------------+
| Ubuntu Agent     |                 | Windows Agent    |
| File Monitoring  |                 | File Monitoring  |
+------------------+                 +------------------+
                            |
                            |
                    VirusTotal API
                            |
                    Threat Intelligence
                            |
                            |
                  Wazuh Dashboard Alerts
```

---

# 🛠 Technologies Used

- Ubuntu Server 22.04 LTS
- Wazuh SIEM
- Wazuh Dashboard
- Wazuh Manager
- Wazuh Agent
- File Integrity Monitoring (FIM)
- VirusTotal API
- VirtualBox
- PuTTY
- MobaXterm

---

# 📂 Repository Structure

```
Security Monitoring Lab (SOC Lab)
│
├── Lab-1 Ubuntu Installation
├── Lab-2 Wazuh Installation
├── Lab-3 Wazuh Agent Configuration
├── Lab-4 VirusTotal Integration
│
├── screenshots/
│
├── commands/
│
└── README.md
```

---

# 🚀 Lab Workflow

## Step 1

Install Ubuntu Server inside VirtualBox.

---

## Step 2

Install and configure Wazuh Manager.

---

## Step 3

Access the Wazuh Dashboard.

---

## Step 4

Install and register Wazuh Agent.

---

## Step 5

Verify successful agent connection.

---

## Step 6

Enable File Integrity Monitoring (FIM).

---

## Step 7

Integrate VirusTotal API with Wazuh.

---

## Step 8

Generate a test file and modify/delete it.

---

## Step 9

Observe generated alerts inside Wazuh Dashboard.

---

# 🔍 Features

- Ubuntu Server Deployment
- Wazuh SIEM Installation
- Endpoint Monitoring
- Agent Registration
- File Integrity Monitoring
- VirusTotal Threat Intelligence
- Real-Time Alert Detection
- Security Event Monitoring
- Dashboard Visualization

---

# 📸 Screenshots

This repository contains screenshots for every important step including:

- Ubuntu Installation
- Wazuh Installation
- Dashboard Login
- Agent Registration
- Agent Active Status
- VirusTotal Configuration
- File Monitoring
- Alert Generation
- Wazuh Dashboard Alerts

---

# 📖 Learning Outcomes

After completing this lab, I learned how to:

- Deploy a SIEM platform
- Configure Wazuh Manager
- Connect endpoint agents
- Monitor endpoint activities
- Configure File Integrity Monitoring
- Integrate external Threat Intelligence
- Detect malicious file events
- Analyze security alerts
- Perform basic SOC monitoring tasks

---

# 📚 Skills Demonstrated

- Cyber Security
- SOC Operations
- SIEM
- Wazuh
- Ubuntu Linux
- Threat Intelligence
- VirusTotal
- File Integrity Monitoring
- Endpoint Security
- Security Monitoring
- Incident Detection

---

# 🚀 Future Improvements

The following enhancements are planned to extend this Security Monitoring Lab into a more advanced SOC environment:

- Implement Security Orchestration, Automation and Response (SOAR) for automated incident response.
- Integrate MISP (Malware Information Sharing Platform) as an external Threat Intelligence Platform (TIP).
- Configure automated IOC (Indicators of Compromise) enrichment using MISP.
- Correlate Wazuh alerts with MISP threat intelligence feeds.
- Enable automated malware hash reputation checks using multiple threat intelligence sources.
- Develop custom detection and correlation rules for advanced attack detection.
- Implement MITRE ATT&CK mapping for improved threat classification.
- Integrate Sigma rules for standardized detection capabilities.
- Configure Active Response to automatically isolate or block malicious activities.
- Add email notifications for critical security alerts.
- Integrate Slack or Microsoft Teams for real-time SOC notifications.
- Deploy additional Windows and Linux endpoints for multi-agent monitoring.
- Monitor web server, SSH, and authentication logs for suspicious activities.
- Integrate Suricata IDS for network intrusion detection.
- Add YARA-based malware detection and scanning.
- Develop custom SOC dashboards for security analytics and reporting.
- Integrate TheHive and Cortex for incident management and automated analysis.
- Implement compliance monitoring (PCI-DSS, CIS Benchmarks, ISO 27001).
- Create automated reporting and alert summarization.
- Build a complete Enterprise SOC Lab architecture for blue team practice.

# 👨‍💻 Author

**Naziur Rahman Nabil**

Cyber Security Engineering Student

University of Frontier Technology Bangladesh (UFTB)

---

## ⭐ If you found this project useful, consider giving it a Star.
