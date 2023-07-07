<h1>Active Directory Home Lab With Powershell user creation</h1>

<h2>Description</h2>
This project is a walkthrough of how I created an Active Directory home lab Environment using Oracle VirtualBox. I configured a Microsoft Server so that it could run Active Directory. Then I set up a Domain Controller so I can manage a domain. Then, using a PowerShell script, I established over 1000 new users in Active Directory, and I logged into those accounts on a different client using the domain I had constructed to access the internet. This lab mimics a workplace setting. For this lab, I'll need a Powershell script, a Windows 10 Enterprise ISO, Oracle VirtualBox, and a Microsoft Server 2019 ISO..
<br />

<h2>Languages and Utilities Used</h2>

- <b>Active Directory</b> 
- <b>PowerShell</b>
- <b>CMD</b>

<h2>Environments Used </h2>

- <b>Oracle VirtualBox</b>
- <b>Microsoft Server 2019</b>
- <b>Windows 10</b>

<h2>Links</h2>

- [<b>Oracle VirtualBox</b>](https://www.virtualbox.org/wiki/Downloads)
- [<b>Microsoft Server 2019</b>](https://www.microsoft.com/en-us/evalcenter/download-windows-server-2019)
- [<b>Windows 10 ISO</b>](https://www.microsoft.com/en-us/software-download/windows10)

<h2 align="center">Program walk-through</h2>

<p align="center">
<b>The network diagram I'll be using for this project</b> <br/>
<img src="https://i.imgur.com/C6XQLhT.png" height="80%" width="80%" alt="Network Diagram"/>
<br />
<br />

<b>Create a new virtual machine by clicking on "New" in VirtualBox, naming it "DC," and selecting the "Windows Server 2019" ISO file as the boot media.<b>


<img src="https://i.imgur.com/RPXsvMV.png" />

<b>For the Virtual Machine that will be hosting my Domain Controller, I need two network adapters. I need the NAT that will use my host IP address from my home router and an Internal Network Adapter so that my DC can communicate with other Virtual Machines.</b> <br/>
<img src="https://i.imgur.com/IxxBJRD.png"/>
<br />
<br />
<br/>
<img src="https://i.imgur.com/wS1Lghe.png"/>
<br />
<br />

<h2>Launch the virtual machine and install Server 2019 (make sure to select "Windows Server 2019 Standard Evaluation (Desktop Experience)" For GUI)<h2>

<img src="https://i.imgur.com/iAWdxwN.png"/>

<b> Select custom install so we can format the drive

<img src="https://i.imgur.com/CledkDg.png"/>

## Assign IP addressing for the internal network.

<img src="https://i.imgur.com/7yKM42Z.png"/>
<img src="https://i.imgur.com/MNg9t9A.png"/>


##  Name the server and install Active Directory to create the domain.
<img src="https://i.imgur.com/FvZPoWt.png"/>

<img src="https://i.imgur.com/Qj1dVe6.png"/>

<h2>Configure routing so that clients on the private network can access the internet through the domain controller.<h2>

<img src="https://i.imgur.com/6KcYK3Q.png"/>
<img src="https://i.imgur.com/jN2XjwK.png"/>

<h2>Set up DHCP on the domain controller.</h2>

<img src="https://raw.githubusercontent.com/AdiH8/Active-Directory-Lab/main/attachments/Pasted%20image%2020230402154312.png"/>
<img src="https://raw.githubusercontent.com/AdiH8/Active-Directory-Lab/main/attachments/Pasted%20image%2020230402154041.png"/>
<img src="https://raw.githubusercontent.com/AdiH8/Active-Directory-Lab/main/attachments/Pasted%20image%2020230402154439.png"/>

<h2>Run Powershell script to add 1000 users in the Active Directory</h2>

- [<b>Create Accounts Script</b>](https://github.com/joshmadakor1/AD_PS)

<img src=https://i.imgur.com/JquWAyt.png/>

<h2>Create a new virtual machine named "Client1" and install the Windows 10 ISO.</h2>

<img src="https://i.imgur.com/HUQgQ6W.png">

Change the adapter to the internal network
<img src="https://i.imgur.com/fDWu3XH.png">

<h2>Connect the client machine to the private network and join it to the domain.</h2>

<img src="https://raw.githubusercontent.com/AdiH8/Active-Directory-Lab/main/attachments/Pasted%20image%2020230402155807.png"/>
