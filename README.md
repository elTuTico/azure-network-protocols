<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, we observe various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04

<h2>High-Level Steps</h2>

- Step 1
- Step 2
- Step 3
- Step 4

<h2>Actions and Observations</h2>

<p>
<img src="https://github.com/elTuTico/azure-network-protocols/assets/137955237/6170fa81-5e83-4f25-b1a6-cd916c08cf52" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Log into portal.azure.com and from the home page type “Resource Group” into the search bar.
</p>
<br />

<p>
<img src="https://github.com/elTuTico/azure-network-protocols/assets/137955237/55a20f35-ef0e-4a7a-940e-e384a9aa0166" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Click on “create resource group” and name the group something that pertains to the activities that will be hosted within it, for example: NetworkProtocol. Have the location be consistent from the Resource Group to the Virtual Machines. Finish the Group by following the other prompts and leaving the additional modifications on default. 
</p>
<br />

<p>
<img src="https://github.com/elTuTico/azure-network-protocols/assets/137955237/b080f49c-5d53-453a-9020-0f18f38f955a" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Navigate back home and this time within the search bar look up “Virtual Machines”. Click on “Create” and select “Azure virtual machine”.
</p>
<br />

<p>
<img src="https://github.com/elTuTico/azure-network-protocols/assets/137955237/98d87f3e-ca29-4ca5-8887-37cc33dc1dcc" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
The first Virtual Machine will be a Windows 10 Pro, version 22H2 - x64 Gen2. Located within the Resource Group that was just made along with the same region. Have the size of this VM “Standard_E2s_v3 - 2 vcpus, 16 GiB memory and keep the rest of the other settings on default.
</p>
<br />

<p>
<img src="https://github.com/elTuTico/azure-network-protocols/assets/137955237/89c75731-3277-4e8b-bb3e-2ce354565a96" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
The second Virtual Machine will be a Linux (Ubuntu) Server 20.04 LTS - x64 Gen2 that will be in the Resource Group that was created within the same region. Set the “Authentication type” to “Password” and configure the credentials. Before seeing if this VM validation passes, ensure that within the “Networking” tab the Vnet matches the Virtual Network made by the Windows VM.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/DJmEXEB.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
