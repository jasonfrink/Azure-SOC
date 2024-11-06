<h1>Microsoft Azure SOC Home Lab</h1>

<h2>Description</h2>

This project walk-through details the setup of a personal Security Operations Center (SOC) using Microsoft Azure and Microsoft Sentinel as a Security Information and Event Management (SIEM) solution. With this setup, I created a simulated environment to monitor, log, and alert on potential security events across a virtual machine and connected resources. This hands-on project is ideal for cybersecurity professionals looking to gain experience with threat detection, log analysis, and incident response, all within a cost-effective, cloud-based setup. Through this lab, I configured alerts, implemented threat intelligence feeds, and enabled real-time monitoring. This project provides a foundational experience in building and managing a SOC environment, using tools and processes similar to those deployed in real-world enterprise security setups.
<br>

<h3>Enviroment Creation</h3>

-Setup Azure environment and resource group creation. The resource group will contain all the project's resources for easier management and organization.

- <b>Microsoft Azure</b>
- <b>Microsoft Sentinel</b>

The first step is setting up the Azure VM. The machine is set up from the Azure main menu. For the lab, the preset configurations are used.
<br>
![image](https://github.com/user-attachments/assets/bde790f1-2deb-41c1-b5ab-8cf681a94636)
<br>
There are numerous menus options to complete for setting up the VM. You can see in the image many of the options available. The VM created is Windows 10 Pro, configured with Port 3389 (RDP) open and public IP address for networking.
<br>
![image](https://github.com/user-attachments/assets/5db8aa81-64e4-4aed-add7-6df6abb98a80)

After the Windows VM is running, we want to set up Microsoft Sentiel. It's a simple process, just search for Sentinel in the menu and follow the prompts. Sentinel needs to be added to the Azure resource group being used for the VM. 

![image](https://github.com/user-attachments/assets/f287f8e8-226c-4fb4-9586-f6a54d4c4adf)
<br>
Part of the Sentinel setup process involves creating a log analytics workspace and then adding Sentinel to that workspace. In the image below, Sentinal has been added to the AzureSOC-LogAnalytics workspace.
<br>

![image](https://github.com/user-attachments/assets/64dc8b06-10cb-442d-9ff7-6d5659f97aae)





