# 🛡️ Wazuh Home Lab – SOC Monitoring Project

## 📌 Overview
This project documents my **home SOC lab** built to practice **SIEM deployment, log collection, and threat detection** using **Wazuh**.  
I deployed a Wazuh Manager and connected both Linux and Windows endpoints via Wazuh Agents to simulate a real-world SOC environment.  

## 🎯 Objectives
- Install and configure a centralized Wazuh Manager.  
- Deploy agents on Linux (Ubuntu) and Windows endpoints.  
- Collect and analyze logs in real time.  
- Simulate security events (failed logins, file changes, suspicious processes).  
- Document steps clearly for reproducibility.  

---

## 🏗️ Lab Architecture

- **Host platform**: VMware Workstation  
- **Wazuh Manager**: Ubuntu Server (latest LTS)  
- **Wazuh Agents**:  
  - Ubuntu Desktop (Linux endpoint monitoring)  
  - Windows 10/11 (Windows endpoint monitoring)  

---
## ⚙️ Setup & Installation

### 1️⃣ Wazuh Manager (Ubuntu Server)
```bash
# Update system
sudo apt update && sudo apt upgrade -y

# Install Wazuh Manager
curl -sO https://packages.wazuh.com/4.x/wazuh-install.sh
sudo bash ./wazuh-install.sh -i
