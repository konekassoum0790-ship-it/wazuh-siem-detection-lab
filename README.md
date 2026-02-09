# 🔐 Network Incident Detection Lab (Wazuh SIEM)

## 📌 Overview
This project demonstrates the deployment and configuration of a **Security Operations Center (SOC)** environment using **Wazuh SIEM**. The goal was to build a robust detection pipeline to identify, analyze, and mitigate network attacks in real-time.

---

## 🏗️ Architecture
- **SIEM Manager:** Wazuh (deployed on Ubuntu Server)
- **Monitoring Agents:** Debian 12 & Windows Server endpoints
- **Attacker Machine:** Kali Linux (Metasploit, Nmap, Hydra)
- **Virtualization:** Proxmox / VMware

---

## 🛠️ Key Features & Implementation

### 1. Threat Detection (Custom Rules)
I developed custom XML correlation rules to detect specific attack patterns that standard decoders might miss.
*Example: SSH Brute Force Detection Rule*
```xml
<group name="syslog,sshd,">
  <rule id="100001" level="10">
    <if_sid>5712</if_sid>
    <match>Failed password for</match>
    <description>Custom Alert: Multiple failed SSH login attempts detected</description>
    <mitre>
      <id>T1110</id>
    </mitre>
  </rule>
</group>
```
2. Incident Response & Forensic
Log Correlation: Analysis of security events across multiple endpoints.
IOC Extraction: Identified malicious IPs and payloads during simulated attacks.
MITRE ATT&CK Mapping: Every incident report follows the MITRE framework for professional-grade compliance.

📂 Project Documentation
The complete methodology, attack scenarios (ARP Poisoning, SSH Brute Force), and remediation steps are detailed in the official report:
👉 **[Download Full Incident Report (PDF)](./doc/Wazuh_rapport.pdf)**


🚀 Skills Demonstrated
SIEM Administration (Wazuh)
Network Security (VLAN isolation, SSH Hardening)
Threat Hunting (Log analysis, Syscheck)
Technical Reporting (Incident timeline, remediation)

Contact: konekassoum0790@gmail.com |www.linkedin.com/in/kassoum-kone-836255271
