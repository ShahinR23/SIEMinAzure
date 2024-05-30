<h1>VM Honeypot and SIEM in Azure</h1>

<h2>Objective</h2>
Developed a custom-based SIEM using Microsoft Azure Sentinel. SIEM (Security Information and Event Management) helps organizations detect, analyze, and respond to security threats.

<br />

<h2>Project Overview:</h2>

1. **Setting Up a Honeypot:** I created a Windows 11 virtual machine (VM) in Azure to act as our honeypot.
2. **Logging Events**: I configured Azure Log Analytics to store logs from our honeypot.
3. **PowerShell Scripting:** I extracted relevant events from the VM using a PowerShell script and a third-party API.
4. **Azure Sentinel Configuration**: Finally, I used Azure Sentinel to visualize the attacks on our honeypot.

<h2>Project Walk-Through:</h2>

<h3>Creating a Virtual Machine</h3>

1. I went to the Azure Portal and searched for "Virtual machines".

2. I clicked “Create” and select “Azure virtual machine”.

3. I filled in the details:
- **Subscription:** Azure Subscription 1
- **Resource Group:** Created a new one named Honeypot_group
- **Virtual Machine name**: Chose a name of my liking
- **Region:** (US) West US 3
- **Image:** Windows 11 Pro
- **Size:** Standard size
- **Administrator account:** Created and saved the credentials

4. I clicked “Review + Create” and waited for Azure to deploy the VM.

5. Once the VM was created, I changed the firewall rules to allow all incoming traffic:
- Went to the VM's dashboard, then to “Networking” > “Add Inbound port Rule”.
- Added the necessary configurations to allow all traffic.

 <br/>
<img src="https://imgur.com/fHKCjfm.png" height="80%" width="80%" alt="Building Home Network Steps"/>
<br />

<h3>Setting Up Log Analytics Workspace</h3>

1. I searched for “Log Analytics Workspace” in the Azure Portal and clicked “Create”.
2. I filled in the details and created the workspace.
3. I configured the workspace to log events from the VM:
- Went to “Microsoft Defender for Cloud” > “Environment Settings” > “Log-Honeypot”.
- Turned on the Server plan in “Defender Plan”.
- In “Data Collection”, select “All Events”.
  
<br/>

<img src="https://imgur.com/dCmvCkb.png" height="80%" width="80%" alt="Building Home Network Steps"/>
<br />

<h3>PowerShell for Custom Events</h3>

1. I connected to the VM using Remote Desktop Protocol (RDP):
- I searched for Remote Desktop in Windows and connected using the VM’s public IP and my credentials.
2. I disabled the firewall inside the VM:
- Went to Start > Windows Defender Firewall properties and turned off all profiles.
3. I used a PowerShell script to capture specific events:
- Signed up for an API key at ipgeolocation.io.
- Used the provided PowerShell script from GitHub, inserted my API key, and ran the script.
- The script logged failed login attempts (event ID 4625) to **C:\Program\failed_rdp.log**.
 
<br/>

<img src="https://imgur.com/Ut9GYmf.png" height="80%" width="80%" alt="Building Home Network Steps"/>

<br />

<h3>Azure Sentinel Configuration</h3>

1. I created Custom Logs in Log Analytics:
- Went to Log Analytics Workspace, selected my workspace, then Tables > Create (New Custom log MMA-based).
- Uploaded a sample **failed_rdp.log** file.
- Specified the collection path (**C:\ProgramData\failed_rdp.log**).
- Named the custom log and created it.
2. I visualized logs in Azure Sentinel:
- I went to Sentinel on the Azure Portal.
- Added my Log Analytics Workspace to Sentinel.
- Created a new workbook in Sentinel and added a query to filter and visualize the data.
- I visualized the data on a map in Sentinel by configuring the workbook settings.
 
<img src="https://imgur.com/JRgqAyq.png" height="80%" width="80%" alt="Building Home Network Steps"/>
<br />
<br />

</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
