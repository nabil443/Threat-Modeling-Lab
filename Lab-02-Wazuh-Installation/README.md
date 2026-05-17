# Lab 02 - Wazuh Installation

## Objective

To install and configure Wazuh SIEM on Ubuntu Server for security monitoring and threat detection.

---

## Environment

* Ubuntu Server 22.04
* VirtualBox
* Wazuh SIEM 4.7.5

---

## Installation Steps

### Step 1: Update System

```bash
sudo apt update && sudo apt upgrade -y
```

### Step 2: Download Wazuh Installer

```bash
curl -O https://packages.wazuh.com/4.7/wazuh-install.sh
```

### Step 3: Give Execute Permission

```bash
chmod +x wazuh-install.sh
```

### Step 4: Install Wazuh

```bash
sudo ./wazuh-install.sh -a
```

---

## Verification

### Check IP Address

```bash
ip a
```

### Access Dashboard

```text
https://SERVER_IP
```

---

## Result

Wazuh SIEM was successfully installed and accessed through the web dashboard.

---

## Screenshots

* Ubuntu terminal
* Wazuh installation process
* Wazuh dashboard login
* Wazuh dashboard home page
