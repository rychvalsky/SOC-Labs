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

# Verify service is running:
sudo systemctl status wazuh-manager
```

### 2️⃣ **Wazuh Agent (Ubuntu Client)**
```bash
# Download and install agent
curl -sO https://packages.wazuh.com/4.x/wazuh-install.sh
sudo bash ./wazuh-install.sh -a

# Register agent with manager
sudo /var/ossec/bin/agent-auth -m <WAZUH_MANAGER_IP>
sudo systemctl start wazuh-agent
```
### 3️⃣ Wazuh Agent (Windows Client)

Download the Wazuh Agent MSI from Wazuh Downloads
.

During installation:

Enter Wazuh Manager IP.

Choose agent name (hostname recommended).

After installation, start the service:
``` bash
(powershell) net start wazuhsvc
```

## 🔍 Validation & Testing
### ✅ Agent Connectivity

Confirm in Wazuh dashboard → Agents → Connected.

### ✅ Simulated Events

Failed Login (Linux/Windows)

Multiple failed SSH or RDP login attempts.

Expected: Brute-force alert in Wazuh.

File Integrity Monitoring (FIM)

Modify /etc/hosts or create a test file.

Expected: FIM alert in Wazuh.

Suspicious Process Execution

Run PowerShell command or netcat.

Expected: Process creation alert.

(Add screenshots here)
---
## 📸 Screenshots

Wazuh Dashboard with agents connected.

<img width="1683" height="1082" alt="image" src="https://github.com/user-attachments/assets/4652cc17-418f-4d54-9d7a-9dcd8a736e6f" />


Example alert (failed login).

<img width="1656" height="1048" alt="image" src="https://github.com/user-attachments/assets/ecbf1a6a-e927-46d0-a20e-45712e2d2e56" />

<img width="1656" height="1057" alt="image" src="https://github.com/user-attachments/assets/50fb7ab1-ed3e-4844-aa6e-0f1a67576084" />


--
**File integrity alert. (new file, file updated ,file deleted)**

<img width="1643" height="1042" alt="image" src="https://github.com/user-attachments/assets/20e5d52f-b8f8-4740-880d-5a3b35e1703e" />


---

## 📚 Skills Learned

SIEM deployment and management.

Linux and Windows endpoint monitoring.

Log collection and correlation.

Incident simulation and detection.

Documentation and technical writing.

---
## 🔗 References

Wazuh Official Documentation

Wazuh GitHub
