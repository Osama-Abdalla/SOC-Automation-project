# SOC-Automation-project

## 📖 Project Overview

This project automates a key Security Operations Center (SOC) workflow. It connects a security monitoring tool (Wazuh) with a Security Orchestration, Automation, and Response (SOAR) platform (TheHive) to automatically create and enrich incidents, significantly reducing manual effort for SOC analysts and accelerating response times.


## 🛠️ Tech Stack & Tools

*   **SIEM / EDR:** [Wazuh](https://wazuh.com/)
*   **SOAR Platform:** [Shuffle](https://shuffler.io/)
*   **Case Management:** [TheHive](https://strangebee.com/thehive/)
*   **Infrastructure:** Docker, Virtual Machines.




## 🔄 Automated Workflow Logic

The following diagram illustrates the automated incident response pipeline:

<img width="849" height="641" alt="image" src="https://github.com/user-attachments/assets/5d5146a7-6474-4410-ba25-0559aef1c4a2" />

## Configeration 
## 1. Wazuh Manager
- We began the project by establishing our core detection capability, deploying the Wazuh manager on an Ubuntu server virtual machine. This formed the foundation of our security monitoring, providing log analysis, intrusion detection, and vulnerability assessment for our endpoints.

<img width="1750" height="937" alt="image" src="https://github.com/user-attachments/assets/06e483a2-e1a3-48e9-81a2-3d3b87dcff49" />

## 2.Wazuh Agent
- Following the successful deployment of the Wazuh manager, the next critical step was to deploy and configure the Wazuh agents on our endpoint, a Windows 11 client. This involved installing the agent software and then securely registering it with the manager by specifying the manager's IP address. Once the agent-manager communication was established, the endpoint immediately began streaming vital security telemetry—including system logs, process activity, and network data—to the central manager for real-time analysis and correlation. This provided us with the essential visibility needed to detect potential threats.

<img width="1778" height="969" alt="image" src="https://github.com/user-attachments/assets/18a28c9e-5f31-447f-bccf-c76a1afc8c38" />
<img width="1769" height="871" alt="image" src="https://github.com/user-attachments/assets/2f566261-52ce-4e23-80f3-cd6495c3893d" />

- Opening windows event viewer to forword sysmon events from the agent to wazuh manager.
  
![5963116230397251224](https://github.com/user-attachments/assets/6b66b194-fe08-448a-9646-07fecb9d3d3b)

- Edit wazuh agent ossec.config file (need admin prevelige) .Then adding the IP adress of the manager to forword events.
  
![5963116230397251225](https://github.com/user-attachments/assets/cfa7b590-dae2-4781-a7ae-3dffdfed1054)



## 🚀 Key Features & Achievements

*   **Full Automation from Detection to Triage:** Eliminates the need for an analyst to manually create incidents in the SOAR platform.
*   **Intelligent Alert Enrichment:** Automatically enriches incidents with threat intelligence (IOCs) for better context and faster decision-making.
*   **Proactive Analyst Notification:** Immediately notifies the SOC team via email when a new, high-priority incident is created.
*   **Reduced Mean Time to Respond (MTR):** Cut down the time from initial detection to analyst awareness from several minutes to seconds.


