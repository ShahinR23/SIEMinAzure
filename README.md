<h1>Honeypot and SIEM in Azure</h1>

<h2>Objective</h2>
Developed a custom-based SIEM using Microsoft Azure Sentinel. SIEM (Security Information and Event Management) helps organizations detect, analyze, and respond to security threats.

<br />


<h2>Project Walk-Through:</h2>


<h3>Step 1: Added Network Devices to the Workspace</h3>

I began by adding essential network devices to the Logical Workspace. This included a PC, a laptop, and a cable modem. The cable modem was connected to the Internet Service Provider (ISP) via a coaxial cable and to the local network through an Ethernet cable. The devices were added using the Device-Type Selection Box:
- **PC:** End Devices > End Devices > PC
- **Laptop:** End Devices > End Devices > Laptop
- **Cable Modem:** Network Devices > WAN Emulation > Cable Modem
 <br/>
<img src="https://imgur.com/fHKCjfm.png" height="80%" width="80%" alt="Building Home Network Steps"/>
<br />

<h3>Step 2: Changed Display Names of the Network Devices</h3>

Next, I changed the display names of the network devices for clarity:
- Clicked on each device icon in the Logical Workspace.
- Selected the Config tab in the device configuration window.
- Updated the Display Name field to "Shahin PC," "Laptop," and "Cable Modem."
  
<br/>

<img src="https://imgur.com/dCmvCkb.png" height="80%" width="80%" alt="Building Home Network Steps"/>
<br />

<h3>Step 3: Added Physical Cabling Between Devices</h3>

I added the necessary physical cabling between the devices:
- **PC to Wireless Router:** Used a copper straight-through cable to connect the FastEthernet0 interface of the PC to the Ethernet 1 interface of the wireless router.
- **Wireless Router to Cable Modem:** Connected using a copper straight-through cable between the internet interface of the wireless router and the Port 1 interface of the cable modem.
- **Cable Modem to Internet Cloud:** Connected the Port 0 interface of the cable modem to the Coaxial 7 interface of the Internet cloud using a coaxial cable.
 
<br/>

<img src="https://imgur.com/Ut9GYmf.png" height="80%" width="80%" alt="Building Home Network Steps"/>

<br />
<br />
<h2>Part 2</h2>

<h3>Step 1: Configured the PC</h3>

I configured the PC for the wired network connection:
- Clicked on the PC and navigated to the Desktop tab.
- Verified that DHCP was enabled under IP Configuration, ensuring the PC received an IP address.
 
<img src="https://imgur.com/EqNcLiG.png" height="80%" width="80%" alt="Building Home Network Steps"/>

- Opened the Command Prompt and entered **ipconfig /all** to check the IPv4 addressing information, confirming the PC received an IPv4 address in the 192.168.0.x range.

<img src="https://imgur.com/m6LCMv5.png" height="80%" width="80%" alt="Building Home Network Steps"/>

- Tested connectivity to **cisco.srv** by issuing the **ping cisco.srv** command, receiving four replies to confirm successful connectivity.

<img src="https://imgur.com/Vr3qEjX.png" height="80%" width="80%" alt="Building Home Network Steps"/>

<br />

<h3>Step 2: Configured the Laptop</h3>

Configured the laptop to access the wireless network:
- Clicked on the Laptop and selected the Physical tab.
- I powered off the laptop, removed the Ethernet copper module, and replaced it with the Wireless WPC300N module.
  <br/>
  
<img src="https://imgur.com/evL9UhG.png" height="80%" width="80%" alt="Building Home Network Steps"/>

- I powered the laptop back on and navigated to the Desktop tab.

<img src="https://imgur.com/e9D9mMy.png" height="60%" width="60%" alt="Building Home Network Steps"/>

- Connected to the wireless network by selecting PC Wireless, navigating to the Connect tab, and connecting to the "HomeNetwork."

<img src="https://imgur.com/XJjQcbO.png" height="60%" width="60%" alt="Building Home Network Steps"/>

- Verified connectivity by opening the Web Browser and navigating to cisco.srv.

<img src="https://imgur.com/wFbw7yi.png" height="60%" width="60%" alt="Building Home Network Steps"/>

This project showcased my ability to build and configure a simple network using Packet Tracer, demonstrating my proficiency in deploying network devices, managing physical connections, and ensuring proper device configurations to establish network connectivity.

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
