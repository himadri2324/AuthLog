# AuthLog: Windows Authentication Log Analysis
Analyzes Windows authentication logs using Elastic SIEM to monitor login activity, detect repeated failed authentication attempts, and identify suspicious patterns that may indicate brute-force attacks or unauthorized access to systems in a controlled lab environment.

---

## 🎬 Demonstration
<p align="center">
  <a href="https://github.com/user-attachments/assets/4bc69102-720d-407f-91a0-eab87e8f56f1" target="_blank">
    <img src="https://img.icons8.com/color/96/video.png" alt="Watch Demo" />
    <br>
    <strong>Click to watch the demonstration video</strong>
  </a>
</p>

---

## 📘 Project Overview
This project demonstrates Windows authentication log analysis using Elastic SIEM. It collects security event logs from a Windows system, processes them centrally, and detects repeated failed login attempts. The setup helps identify brute-force behavior and improves visibility into unauthorized authentication activities within a controlled lab environment.

---

## 🎯 **Key Objectives:**
* **Centralized Log Collection:** Collect Windows authentication events centrally for consistent monitoring and analysis.
* **Authentication Failure Detection:** Identify repeated failed login attempts indicating possible brute-force attacks.
* **Real-Time Monitoring:** Monitor authentication activity continuously using Elastic SIEM dashboards and alerts.
* **Security Visibility Improvement:** Improve visibility into login behavior and potential unauthorized access attempts.

---

## 🖥️ **Virtual Machines (VMware Workstation):**
| VM Name | Operating System | Role | 
| :--- | :--- | :--- |
| **Windows-Client** | Windows 10 | Generates authentication and security event logs |
| **Elastic-SIEM** | Ubuntu 22.04LTS | Hosts Elastic Stack for log analysis and detection |

---

## 🔧 **Tools and Roles per Component:**
| Component | Tools/Services | Purpose |
| :--- | :--- | :--- |
| **Log Source** | Windows Event Logs | Generate authentication and security events |
| **Log Collection Agent** | Winlogbeat | Collect and forward Windows Security Event Logs | 
| **Log Processing** | Elasticsearch | Store, index, and process security logs | 
| **SIEM Analysis** | Elastic Security (SIEM) | Detect suspicious authentication patterns | 
| **Visualization** | Kibana | Visualize logs and security alerts | 

---

## 🖧 **Network Architecture Diagram:**
<p align="center">
<img src="https://github.com/himadri2324/AuthLog/blob/main/AuthLog%20Network%20Architecture%20Diagram.png"
  alt="AuthLog Network Architecture Diagram" width="750"/>
  </p>

---

## 🏗️ **Architecture Flow Diagram:**
<p align="center">
  <img src="https://github.com/himadri2324/AuthLog/blob/main/AuthLog%20Architecture%20flow%20Diagram.png" 
       alt="AuthLog Architecture Diagram" width="750"/>
</p>
Visual representation of Windows authentication events flowing from log generation through Elastic SIEM detection to analyst investigation in a controlled lab environment.

---

## ⚙️ **Detailed Setup Steps**
1.  **Environment Preparation:**
    * Install VMware Workstation on the host system
    * Create two virtual machines: Ubuntu 22.04 LTS and Windows 10
    * Allocate sufficient CPU, RAM, and disk resources for Elastic Stack stability
    * Configure NAT-based networking for secure internal VM communication
    * Verify network connectivity between Windows and Ubuntu machines
2.  **Windows Authentication Logging Configuration:**
    * Enable Audit Logon Events and Audit Account Logon Events via Group Policy
    * Configure policies to log both success and failure authentication events
    * Generate failed login attempts to confirm Event ID 4625 is recorded
3.  **Elastic Stack Installation (Ubuntu VM):**
    * Install Elasticsearch for log storage and indexing
    * Install Kibana for log visualization and security dashboards
    * Verify Elasticsearch and Kibana services are running successfully
4.  **Elastic Agent / Winlogbeat Setup (Windows VM):**
    *  Install Elastic Agent or Winlogbeat on the Windows system
    *  Configure agent to collect Security Event Logs
    *  Set Elasticsearch endpoint and authentication details
    *  Validate log forwarding from Windows to Elasticsearch
5. **SIEM Configuration and Detection Rules:**
    * Enable Elastic Security (SIEM) in Kibana
    * Configure detection rules for multiple failed authentication attempts
    * Tune thresholds to reduce false positives
6. **Monitoring and Validation:**
    * Simulate repeated failed login attempts on Windows
    * Verify events appear in Kibana Security dashboards
    * Confirm alerts are generated for suspicious authentication behavior
---

## 🔍 **Detection**
* **Failed Login Event Monitoring:** Detects Windows Event ID 4625 generated during unsuccessful authentication attempts.
* **Repeated Authentication Attempts:** Identifies multiple failed logins from same user or source.
* **SIEM Rule Evaluation:** Applies Elastic SIEM rules to correlate authentication failure patterns.
* **Real-Time Log Ingestion:** Continuously ingests Windows security logs for immediate analysis.

---

## 🛠️ **Response**
* **Security Alert Generation:** Generates SIEM alerts when authentication failure thresholds are exceeded.
* **Incident Visibility:** Displays suspicious login activity clearly on Kibana security dashboards.
* **Manual Investigation Support:** Enables analysts to review source IP, username, and timestamps.
* **Threat Confirmation:** Assists in confirming brute-force behavior through correlated log events.
  
---

## 🚀 Future Enhancements
* **Automated Response Actions:** Automatically block source IPs using firewall or endpoint controls.
* **Account Lockout Integration:** Trigger automated account lockout after repeated authentication failures.
* **Geo-Location Analysis:** Detect abnormal login attempts based on unusual geographic locations.

---

## 🔚 Conclusion
This project demonstrates effective Windows authentication log analysis using Elastic SIEM to detect suspicious login behavior. By centralizing security logs and applying detection rules, it improves visibility into authentication activity. The setup highlights how SIEM solutions help identify brute-force attempts and support timely investigation in a controlled lab environment.
