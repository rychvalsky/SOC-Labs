# SOC-Labs
Hands-on SOC and security monitoring labs (TryHackMe, Wazuh, Splunk, etc.)

# Wazuh TryHackMe Module - SOC Investigation

## 🎯 Objective
Learn how to use Wazuh for log monitoring, rule creation, and incident detection.

## 🛠️ Tools Used
- Wazuh
- Kibana
- Linux log files

## 🔍 Steps Taken
1. Installed and connected Wazuh agent to manager.  
2. Configured monitoring for `/var/log/auth.log`.  
3. Triggered failed SSH login attempts to generate alerts.  
4. Analyzed logs in Kibana dashboard.  
5. Created detection rule for brute force activity.

## ✅ Findings
- Detected repeated failed logins from suspicious IP `203.0.113.5`.  
- Alert generated with Wazuh Rule ID `5710`.  
- Recommended action: block IP at firewall, reset user password.

## 📸 Screenshots
![Wazuh Alert Example](screenshots/alert.png)
