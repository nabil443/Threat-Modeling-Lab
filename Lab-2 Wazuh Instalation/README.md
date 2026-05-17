# Lab 2: Wazuh Installation on Ubuntu Server 22.04

## Student Information

- Name: YOUR NAME
- ID: YOUR ID
- Course: Cyber Security Lab
- Lab Task: Wazuh Installation and Configuration
- Operating System: Ubuntu Server 22.04 LTS

---

# Objective

The objective of this lab is to install and configure Wazuh SIEM platform on Ubuntu Server 22.04 using VirtualBox. The lab also demonstrates SSH connection using PuTTY and accessing the Wazuh Web Dashboard.

---

# Software and Tools Used

1. Oracle VirtualBox
2. Ubuntu Server 22.04 LTS
3. Wazuh SIEM
4. PuTTY
5. Web Browser

---

# System Requirements

- Minimum 4GB RAM
- 2 CPU Cores
- 50GB Storage
- Stable Internet Connection

---

# Network Configuration

- Network Mode: Bridged Adapter
- SSH Enabled: Yes
- Internet Access: Active

---

# Step 1: Ubuntu Server Installation

First, Ubuntu Server 22.04 was installed on VirtualBox.

## Screenshot

![Ubuntu Installation](screenshots/01-ubuntu-server-installed.png)

---

# Step 2: Configure Network

The network adapter was configured as Bridged Adapter to obtain an IP address from the router.

## Screenshot

![Network Configuration](screenshots/02-network-configuration.png)

---

# Step 3: Check IP Address

The following command was used to check the server IP address.

```bash
ip a