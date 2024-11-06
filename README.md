<h1>Microsoft Azure SOC Home Lab</h1>

<h2>Description</h2>

This project walk-through details the setup of a personal Security Operations Center (SOC) using Microsoft Azure and Microsoft Sentinel as a Security Information and Event Management (SIEM) solution. With this setup, I created a simulated environment to monitor, log, and alert on potential security events across a virtual machine and connected resources. This hands-on project is ideal for cybersecurity professionals looking to gain experience with threat detection, log analysis, and incident response, all within a cost-effective, cloud-based setup. Through this lab, I configured alerts, implemented threat intelligence feeds, and enabled real-time monitoring. This project provides a foundational experience in building and managing a SOC environment, using tools and processes similar to those deployed in real-world enterprise security setups.
<br>



-The first step in the labe is creatubg Azure environment and resource group creation. The resource group will contain all the project's resources for easier management and organization.

The machine is set up from the Azure main menu. For the lab, the preset configurations are used. 


![image](https://github.com/user-attachments/assets/bde790f1-2deb-41c1-b5ab-8cf681a94636)


There are numerous menus options to complete for setting up the VM. You can see in the image many of the options available. The VM created is Windows 10 Pro, configured with Port 3389 Remote Desktop Protocol (RDP) open and public IP address for networking. RDP needs to ben enabled to allow remote access to the VM, exposing it to external traffic to simulate potential security events. 


![image](https://github.com/user-attachments/assets/5db8aa81-64e4-4aed-add7-6df6abb98a80)

<h3>Sentinel & Log Analytics</h3>

After the Windows VM is running, we want to set up Microsoft Sentiel. It's a simple process, just search for Sentinel in the menu and follow the prompts. Sentinel needs to be added to the Azure resource group being used for the VM. 


![image](https://github.com/user-attachments/assets/f287f8e8-226c-4fb4-9586-f6a54d4c4adf)


Part of the Sentinel setup process involves creating a log analytics workspace and then adding/connecting Sentinel to that workspace. In the image below, Sentinal has been added to the AzureSOC-LogAnalytics workspace. The log analytics workspace will store and manage logs for analysis. 


![image](https://github.com/user-attachments/assets/64dc8b06-10cb-442d-9ff7-6d5659f97aae)


<h3>Data Connectors Configuration</h3>

In order for Sentinel to analyze the event logs from the Windows 10 VM, we need to add the VM to the log analytics workspace. In the image below, there are currently no computers connected to the log analytics workspace. 

![image](https://github.com/user-attachments/assets/3213c8ea-ea3e-4031-a9a2-08daefe1d74f)

In order to set up this connection, data connectors need to be setup within Sentinel. 

Within the Sentinel workspace, there's an option to at Data Connectors. Using the Content Hub link, we can install the Windows Security Events connector.

![image](https://github.com/user-attachments/assets/7c6bc876-114c-4b68-891f-a33cbea04d15)


Windows Security Events has been installed


![image](https://github.com/user-attachments/assets/d7821b0d-007c-4f21-8bc7-0f5de369f795)


A Data Collection Rule needs to be created as part of the Windows Security Events setup process. 


![2024-11-06_12h07_28](https://github.com/user-attachments/assets/a80b928f-dbcd-4799-93a5-329d58638c1a)


![image](https://github.com/user-attachments/assets/8bc1d9aa-6453-4ccb-9033-0cc6faffc3cb)


<h3>Sentinel Logs</h3>
Now that Sentinel within the log analytics workspace is configured to collect event logs from the Windows10 VM, we want to set up a query for specific types of events. 
