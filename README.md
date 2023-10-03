<h1>Inspecting Traffic Between Azure Virtual Machines</h1>
In this tutorial, various network traffic is observed from Azure Virtual Machines with Wireshark. <br />

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

- Create two virtual machines (Windows & Linux)
- Download WireShark
- Observer multiple types of traffic
- Clean up used resources

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
<img src="https://github.com/elTuTico/azure-network-protocols/assets/137955237/ba3a50ff-6b98-4f16-b162-fffc13483bdd" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
The first Virtual Machine(VM) will be a Windows 10 Pro, version 22H2 - x64 Gen2. Located within the Resource Group that was just made along with the same region. Have the size of this VM “Standard_E2s_v3 - 2 vcpus, 16 GiB memory and keep the rest of the other settings on default.
</p>
<br />

<p>
<img src="https://github.com/elTuTico/azure-network-protocols/assets/137955237/b2654bb9-d6d7-4fbb-ae84-6f3b0d5ec2e8" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
The second VM will be a Linux (Ubuntu) Server 20.04 LTS - x64 Gen2 that will be in the Resource Group that was created within the same region. Set the “Authentication type” to “Password” and configure the credentials. Before seeing if this VM validation passes, ensure that within the “Networking” tab the Vnet matches the Virtual Network made by the Windows VM.
</p>
<br />

<p>
<img src="https://github.com/elTuTico/azure-network-protocols/assets/137955237/3aec33ca-35de-46f4-aed0-640b64bea0e6" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://github.com/elTuTico/azure-network-protocols/assets/137955237/0c7bd15a-55d7-42b2-9bd0-eb367a49b5ca" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://github.com/elTuTico/azure-network-protocols/assets/137955237/501ca1ed-9429-4708-8099-5c310061355b" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Once both VMs have been created, Remote Desktop into the Windows VM. Within this VM open up the browser, search Wireshark, and proceed to download. 
</p>
<br />

<p>
<img src="https://github.com/elTuTico/azure-network-protocols/assets/137955237/f0dfe4fa-9ada-497e-ba3b-ba1a2527cdb7" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://github.com/elTuTico/azure-network-protocols/assets/137955237/f671f7ed-c414-49b2-92c3-b29aa062c33a" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Open up Wireshark and select the Ethernet option. From there navigate to the top left hand for the search bar. From this search bar various types of traffic from the VM can be observed.
</p>
<br />

<p>
<img src="https://github.com/elTuTico/azure-network-protocols/assets/137955237/572e38c1-0a03-4f41-95d5-c4ca3a8f20e9" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://github.com/elTuTico/azure-network-protocols/assets/137955237/d1a3e706-fdfd-4ef8-8e81-b3f5c05ddc26" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Within that search bar filter for DHCP traffic. To observe the variance in the traffic open up Command Prompt by opening up the Start Menu and search “Command Prompt”. From there issue the VM a new IP address by typing ipconfig /renew. 
</p>
<br />

<p>
<img src="https://github.com/elTuTico/azure-network-protocols/assets/137955237/9096f011-ae09-4998-9c23-5d11d6e79954" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://github.com/elTuTico/azure-network-protocols/assets/137955237/159cb66e-392e-402e-b02c-c362bf20371b" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Return to that search bar and type DNS. At first there should be no traffic since there is no active transmission using that Network Protocol. With that Command Prompt used on the last step, search up different web pages IP addresses by typing nslookup "insert webpage".  
</p>
<br />

<p>
<img src="https://github.com/elTuTico/azure-network-protocols/assets/137955237/5b1bfd16-dfad-4207-ab56-ccbbb0a42a80" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next move onto RDP traffic by typing in the Network Protocol tcp.port == 3389. There should be immediate traffic since there is an active Remote Desktop connection onto the Windows VM, therefore traffic is always being transmitted. 
</p>
<br />

<p>
<img src="https://github.com/elTuTico/azure-network-protocols/assets/137955237/ec6bed70-1819-453d-a5e0-233edb710a78" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next observe the variations in traffic for ICMP by typing that into the search bar and opening up Command Prompt. At first there should be no incoming changes to Wireshark, but this will change by pinging to the Linux VM that was made. 
</p>
<br />

<p>
<img src="https://github.com/elTuTico/azure-network-protocols/assets/137955237/64008105-2f4b-4b8c-8c7e-f18347c5fae1" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://github.com/elTuTico/azure-network-protocols/assets/137955237/17b4aeb6-081a-454f-8b00-bc81ee13ac80" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Navigate back to the Azure portal and open up the Linux Virtual Machine that was made, from there find the Private IP Address. Now with the Private IP Address head back to the Command Prompt of the Windows VM and type ping 10.0.0.4 and observe the change in traffic. 
</p>
<br />

<p>
<img src="https://github.com/elTuTico/azure-network-protocols/assets/137955237/760ea32c-dff2-427e-9bd2-8992107502cb" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://github.com/elTuTico/azure-network-protocols/assets/137955237/e9c8b20e-9310-4261-af00-6d6b5a6f3bda" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://github.com/elTuTico/azure-network-protocols/assets/137955237/84d040b8-ad77-4235-ae18-eb92c16b7d29" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://github.com/elTuTico/azure-network-protocols/assets/137955237/bdc1f464-5e0d-43d9-89e4-ef90c241707f" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://github.com/elTuTico/azure-network-protocols/assets/137955237/af622497-40be-4f81-aac0-6a4b4d93041f" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next initiate a perpetual ping from the Windows VM to the Linux VM by typing ping 10.0.0.4 -t. Once the non-stop ping is set up head back to the Azure Portal for the Linux VM. Click on Networking under “Settings” and click on “Add inbound port rule”. Select the ICMP Protocol, Deny, and make the Priority 200. Head back to the Windows VM and observe the change in traffic. Ensure you return to the Azure Portal to reverse the ICMP Protocol to witness the change in traffic. 
</p>
<br />

<p>
<img src="https://github.com/elTuTico/azure-network-protocols/assets/137955237/3cff4c77-4234-4d77-8c71-3f34e0c6b19e" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://github.com/elTuTico/azure-network-protocols/assets/137955237/b0f4bc84-4c95-4b15-a975-4719a42d8d81" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://github.com/elTuTico/azure-network-protocols/assets/137955237/17a671af-b648-4b0c-9311-0a33fb08fef8" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lastly, into the search bar type SSH. To observe the Network Traffic for this protocol open up Command Prompt and type “ssh username@private ip”. Answer yes to continue connecting and enter the password made while creating the VM. This will allow you to remotely connect to the command line of the Linux VM which will create traffic by utilizing commands like username, pwd, ping, and Netcat. Once traffic has been recorded within Wireshark exit out of Command Prompt by typing “exit”. 
</p>
<br />

<p>
<img src="https://github.com/elTuTico/azure-network-protocols/assets/137955237/d9739f1b-672b-4732-823e-a4d4d94f3f84" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
<img src="https://github.com/elTuTico/azure-network-protocols/assets/137955237/479dd12c-a6f4-4947-9a66-6884dadbfedd" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Close out your Remote Desktop connection to the Windows VM. Followed by deleting all of the VMs all at once by deleting the Resource Group made at the beginning of the exercise. To ensure that no resources are being utilized after the completion of the exercise. 
</p>
<br />
