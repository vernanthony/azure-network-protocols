<p align="center">
<img src="https://i.imgur.com/Ua7udoS.png" alt="Traffic Examination"/>
</p>

<h1>Network Security Groups (NSGs) and Inspecting Traffic Between Azure Virtual Machines</h1>






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

- Create and Configure Network Security Groups (NSGs)
- Associate NSGs with Virtual Machines
- Enable Network Security Logging
- Inspect Traffic 

<h2>Actions and Observations</h2>


![image](https://github.com/user-attachments/assets/093a9a31-6ca5-4e37-9301-a3ddbb3918d7)



<p>
</p>
<p>
Created a Windows 10 Virtual Machine and a Linux(Ubuntu) Virtual Machine ensuring both VMs were in the same Virtual Network.</p>
<br />

![Screenshot 2025-01-23 225010](https://github.com/user-attachments/assets/9a04b412-a1c1-4d8e-a00a-7565730b1084)
Downloaded Wireshark to analyze network traffic between both Virtual Machines.

![Screenshot 2025-01-23 225432](https://github.com/user-attachments/assets/34009a72-7043-4000-87f7-82bdf23df4e0)


<p>
</p>
<p>
Applied ICMP filters to isolate and study Internet Control Message Protocol packets for troubleshooting and network diagnostics."</p>
<br />

![Screenshot 2025-01-23 225604](https://github.com/user-attachments/assets/fa79e71c-e293-4cdd-a3ad-790397d722cf)


<p>
</p>
<p>
Attempting to ping Linux Private Ip from Windows VM using Powershell</p>
<br />


![Screenshot 2025-01-23 225632](https://github.com/user-attachments/assets/67e30dda-8948-4026-b608-f95f8169df68)

Obeserved reply from Linux VM
![Screenshot 2025-01-23 225643](https://github.com/user-attachments/assets/77d0e65e-4f71-427e-81e7-1d93c887a934)

Filtered ICMP traffic from communication during ping to Linux VM


<h2>Configuring a Firewall [Network Security Group]</h2>


![Screenshot 2025-01-24 025306](https://github.com/user-attachments/assets/86c42399-7e70-47e1-82a6-ad3f93a12b4a)

Locate Network Security Group/Firewall for Linux VM

![Screenshot 2025-01-24 025456](https://github.com/user-attachments/assets/a9969eae-4030-406d-847a-73f06e761dd0)

Created a rule coming Inbound to the Linux VM

![Screenshot 2025-01-24 030853](https://github.com/user-attachments/assets/112a4b1f-f72a-4b5a-99c8-9e19cb5d2846)


Observed traffic in Windows Powershell after creating rule to deny Incoming ICMPx4 traffic request


![image](https://github.com/user-attachments/assets/4869badf-9a5f-47e6-9a02-79284c9c34f2)


Ran Command prompt in Windows Powershell to generate SSH traffic


![Screenshot 2025-01-24 031932](https://github.com/user-attachments/assets/2757d4da-bde1-408a-9af9-0850e38e7ed7)


Analyzing traffic between both VMs filtered for SSH traffic only
