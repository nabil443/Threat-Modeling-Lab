# Wazuh File Integrity Monitoring (FIM) with VirusTotal Integration

## Overview

This lab demonstrates how to integrate VirusTotal with Wazuh File Integrity Monitoring (FIM). The integration allows Wazuh to monitor file changes in real time and automatically query VirusTotal using the SHA-256 hash of monitored files.

Whenever a file is created, modified, or deleted, Wazuh generates security alerts. If VirusTotal integration is enabled, Wazuh also checks the file reputation against the VirusTotal database.

---

# Lab Objectives

- Install and configure Wazuh File Integrity Monitoring (FIM)
- Configure a monitored directory
- Integrate VirusTotal API with Wazuh
- Generate file events
- Verify security alerts
- Validate VirusTotal integration

---

# Environment

| Component | Version |
|------------|----------|
| Ubuntu Server | 22.04 LTS |
| Wazuh Manager | 4.x |
| VirusTotal API | v3 |
| SSH Client | PuTTY |

---

# Prerequisites

- Ubuntu Server installed
- Wazuh Manager installed
- Internet connection
- VirusTotal Account
- VirusTotal API Key
- sudo privileges

---

# Step 1 : Create VirusTotal Account

Visit

https://www.virustotal.com

Create an account.

Login.

Navigate to

Profile → API Key

Copy your Personal API Key.

---

# Step 2 : Backup Wazuh Configuration

```bash
sudo cp /var/ossec/etc/ossec.conf /var/ossec/etc/ossec.conf.bak
```

---

# Step 3 : Open Wazuh Configuration

```bash
sudo nano /var/ossec/etc/ossec.conf
```

---

# Step 4 : Configure VirusTotal Integration

Inside `ossec.conf` add

```xml
<integration>
    <name>virustotal</name>
    <api_key>YOUR_API_KEY</api_key>
    <group>syscheck</group>
    <alert_format>json</alert_format>
</integration>
```

Replace

```
YOUR_API_KEY
```

with your own VirusTotal API Key.

Save

```
CTRL + O
ENTER
CTRL + X
```

---

# Step 5 : Create Test Directory

```bash
sudo mkdir -p /opt/vt-test
```

Assign ownership

```bash
sudo chown root:wazuh /opt/vt-test
```

Set permissions

```bash
sudo chmod 775 /opt/vt-test
```

Verify

```bash
ls -ld /opt/vt-test
```

Expected Output

```
drwxrwxr-x root wazuh
```

---

# Step 6 : Enable File Integrity Monitoring

Open configuration

```bash
sudo nano /var/ossec/etc/ossec.conf
```

Locate

```xml
<syscheck>
```

Add

```xml
<directories realtime="yes">/opt/vt-test</directories>
```

Example

```xml
<syscheck>

<directories realtime="yes">/home</directories>

<directories realtime="yes">/opt/vt-test</directories>

</syscheck>
```

Save the file.

---

# Step 7 : Restart Wazuh Manager

```bash
sudo systemctl restart wazuh-manager
```

Verify

```bash
sudo systemctl status wazuh-manager
```

Expected

```
active (running)
```

---

# Step 8 : Start Real-Time Alert Monitoring

Open another terminal.

Run

```bash
sudo tail -f /var/ossec/logs/alerts/alerts.json
```

Keep this terminal open.

---

# Step 9 : Generate FIM Alerts

## Create File

```bash
echo "Hello VirusTotal" | sudo tee /opt/vt-test/test.txt
```

Expected Alert

```
File added
```

---

## Modify File

```bash
echo "Modified" | sudo tee -a /opt/vt-test/test.txt
```

Expected Alert

```
Integrity checksum changed
```

---

## Delete File

```bash
sudo rm /opt/vt-test/test.txt
```

Expected Alert

```
File deleted
```

---

# Step 10 : Verify VirusTotal Integration

Check VirusTotal logs

```bash
sudo grep -i virustotal /var/ossec/logs/ossec.log
```

Check Alerts

```bash
sudo grep -i virustotal /var/ossec/logs/alerts/alerts.json
```

Dashboard Search

```
rule.groups:virustotal
```

or

```
virustotal
```

---

# Expected Alerts

## File Added

```
File '/opt/vt-test/test.txt' added
```

---

## File Modified

```
Integrity checksum changed
```

---

## File Deleted

```
File '/opt/vt-test/test.txt' deleted
```

---

## VirusTotal Alert

```
VirusTotal lookup completed
```

or

```
File detected by VirusTotal
```

(depending on the file reputation)

---

# Useful Commands

Restart Wazuh

```bash
sudo systemctl restart wazuh-manager
```

Manager Status

```bash
sudo systemctl status wazuh-manager
```

Monitor Alerts

```bash
sudo tail -f /var/ossec/logs/alerts/alerts.json
```

Check VirusTotal

```bash
sudo grep -i virustotal /var/ossec/logs/ossec.log
```

Check Alerts

```bash
sudo grep -i virustotal /var/ossec/logs/alerts/alerts.json
```

---

# Verification Checklist

- Wazuh Manager Running
- VirusTotal API Configured
- FIM Enabled
- Test Directory Created
- File Created
- File Modified
- File Deleted
- Alert Generated
- VirusTotal Lookup Successful

---

# Screenshots

Include screenshots for

- VirusTotal API Key
- ossec.conf Integration
- syscheck Configuration
- Wazuh Restart
- Test Directory
- File Creation
- File Modification
- File Deletion
- Alert Output
- VirusTotal Dashboard Alert

---

# Conclusion

The integration successfully combines Wazuh File Integrity Monitoring with VirusTotal cloud reputation services. File creation, modification, and deletion events are detected in real time, and suspicious files can be automatically checked against the VirusTotal database, improving threat detection and incident response capabilities.

---

## Author

Name : Naziur Rahman Nabil

Department : Cyber Security Engineering

University : University of Frontier Technology Bangladesh