Lab 2: Wazuh Installation on Ubuntu Server 22.04

## Introduction

Wazuh is an open-source Security Information and Event Management (SIEM) platform used for threat detection, log analysis, intrusion detection, file integrity monitoring, and security monitoring. It provides real-time security visibility and helps detect malicious activities in systems.

In this lab, Wazuh was installed on Ubuntu Server 22.04 running on VirtualBox. The full process includes server setup, network configuration, SSH access using PuTTY, Wazuh installation, and web dashboard access.

---

## Objectives

- Install Ubuntu Server on VirtualBox  
- Configure network settings (Bridged Adapter)  
- Enable SSH access using PuTTY  
- Install Wazuh SIEM platform  
- Access Wazuh Dashboard via browser  
- Verify Wazuh services  

---

## Requirements

### Hardware Requirements
- 4GB RAM minimum  
- 2 CPU cores  
- 50GB storage  
- Stable internet connection  

### Software Requirements
- Oracle VirtualBox  
- Ubuntu Server 22.04 LTS  
- PuTTY SSH Client  
- Web Browser  
- Wazuh installation script  

---

## Step 1: Ubuntu Server Setup

Ubuntu Server 22.04 was installed on VirtualBox successfully.

**Network Mode:** Bridged Adapter  
**Purpose:** To get IP from local router

---

## Step 2: Check IP Address

```bash
ip a

This command is used to find the server IP address.

Step 3: Install SSH Service
sudo apt update
sudo apt install openssh-server -y

Check SSH status:

sudo systemctl status ssh
Step 4: Connect Using PuTTY
Open PuTTY
Enter Ubuntu Server IP address
Port: 22
Login with username and password
Step 5: Update System
sudo apt update && sudo apt upgrade -y
Step 6: Download Wazuh Installer
curl -sO https://packages.wazuh.com/4.7/wazuh-install.sh
chmod +x wazuh-install.sh
Step 7: Install Wazuh
sudo bash ./wazuh-install.sh -a

This command installs:

Wazuh Manager
Wazuh Indexer
Wazuh Dashboard

Installation may take 20–40 minutes.

Step 8: Wazuh Credentials

After installation:

Username: admin
Password: Automatically generated during installation
Step 9: Access Wazuh Dashboard

Open browser:

https://YOUR-SERVER-IP

Example:

https://192.168.0.105

If browser shows warning:

👉 Click Advanced → Proceed

Step 10: Dashboard Login

After login, Wazuh dashboard home page will appear with security monitoring overview.

Step 11: Verify Services
sudo systemctl status wazuh-manager
sudo systemctl status wazuh-dashboard
sudo systemctl status wazuh-indexer
Result

Wazuh SIEM was successfully installed and configured on Ubuntu Server 22.04. SSH connection using PuTTY and dashboard access via browser were successfully tested.

Conclusion

This lab demonstrates practical knowledge of SIEM deployment using Wazuh, Ubuntu server administration, SSH configuration, and security monitoring setup in a virtual environment.
