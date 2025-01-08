<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>
In this project, i observed various network traffic to and from Azure Virtual Machines with Wireshark as well as experiment with Network Security Groups. <br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools
- Various Network Protocols (SSH, RDH, DNS, HTTP/S, ICMP)
- Wireshark (Protocol Analyzer)

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Ubuntu Server 20.04



<h2>Actions and Observations</h2>

<p>
<img src="https://i.imgur.com/GXfx1BJ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
I first started by creating a resource group inside of Azure. I named this resource group RG-network activities.
</p>
<br />

<p>
<img src="https://i.imgur.com/xKN3G29.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Here is a photo of me creating the Linux virtual machine in Azure. I created this VM using the resource group i had previously created. I chose the password option and made a login username and password for both the Linux and Windows VMs.
</p>
<br />

<p>
<img src="https://i.imgur.com/AgC03iN.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In this slide i put the virtual network to be the same virtual network for the windows VM that i had previously created. (i did not showcase the creation of the windows VM because it was a similar process minus a few steps).
</p>
<br />
<p>
<img src="https://i.imgur.com/uOaBKWa.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
I connected to the windows virtual machine using remote desktop. I then downloaded and opened wire shark as well as powershell. I was able to ping the Linux VM using its private IP address and observe the traffic when filtering for ICMP.
</p>
<br />
<p>
<img src="https://i.imgur.com/bpPwnRH.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
In this part of the project i went over to Azure and created an inbound security rule. In the security rule i denied any inbounc traffic to the Linux VM and set a high priority.
</p>
<br />
<p>

<p>
<img src="https://i.imgur.com/ZHB0rXt.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
After creating the security, i went back into the Windows VM and pinged the linux VM using ping -t and eventually the request timed out because thei nbound traffic was blocked.
</p>
<br />
