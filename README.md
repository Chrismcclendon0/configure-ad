# configure-ad
<p align="center">
<img src="https://i.imgur.com/pU5A58S.png" alt="Microsoft Active Directory Logo"/>
</p>

<h1>On-premises Active Directory Deployed in the Cloud (Azure)</h1>
This tutorial outlines the implementation of on-premises Active Directory within Azure Virtual Machines.<br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Active Directory Domain Services
- PowerShell

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows 10 (21H2)

<h2>High-Level Deployment and Configuration Steps</h2>

- Step 1
- Step 2
- Step 3
- Step 4

<h2>Deployment and Configuration Steps</h2>

![image](https://github.com/Chrismcclendon0/osticket-prereqs/assets/144953146/f8d2ca82-0297-4bfb-883a-e33322df86e3)

</p>
<p>
First enter the official Microsoft Azure website and create your subscrption and tenant. Using the search bar, type and select "virtual machines", and click create. </p>
<br />

![image](https://github.com/Chrismcclendon0/osticket-prereqs/assets/144953146/ae086b52-5eba-4c8c-a8c3-650289d97519)


</p>
<p>
Allow Azure to auto create a resource group. Name your virtual machine "DC-1", select desired region, and change "Image" to "Windows 10". Once completed create your username and passsword followed by confirming your "Licensing" by checking the respective box. 

</p>
<br />


![image](https://github.com/Chrismcclendon0/osticket-prereqs/assets/144953146/f09c04be-5c99-41b5-870d-41677ffa73a6)

</p>
<p>
Next select the "Networking" tab and confirm that the "Virtual network, subnet, and Public IP" will all be created by default. Once completed select "Review and create" to create your virtual machine. Create a second virtual machine and name it "Client-1"(this machine will be the directory), and make sure to place in the same region, resource group, and virtual network.
Go into DC-1 virtual machine settings and change IP address to static. 


![image](https://github.com/Chrismcclendon0/configure-ad/assets/144953146/92856c2b-4ae7-4dea-b864-b329a233af52)

Copy the public IP address of Client-1 virtual machine and use remote desktop to connect to the virtual machine. Do the same for virtual machine DC-1.
<p>

![image](https://github.com/Chrismcclendon0/configure-ad/assets/144953146/851cf49e-ac14-4d70-af16-ffb49efd43b6)

In DC-1, go to "Windows defender firewall" and select "Inbound rules". Enable rule on both "core networking diagnostics ICMPv4.

![image](https://github.com/Chrismcclendon0/configure-ad/assets/144953146/989dd8f9-bb7a-4f79-9976-a9f93f8c309f)

![image](https://github.com/Chrismcclendon0/configure-ad/assets/144953146/df66815f-40d9-4385-b928-7e2ce49115e9)


In DC-1 go into server manager-> roles and features and install Active directory Domain services. Promote server to domain controller. 

![image](https://github.com/Chrismcclendon0/configure-ad/assets/144953146/340f37ed-738a-4895-8a4b-722b0e5a26e9)

![image](https://github.com/Chrismcclendon0/configure-ad/assets/144953146/5cc70131-f93d-402e-93ef-17cdebaa3be5)

Add a new forest and create domain name (mydomain.com) and password. Remote desktop will need to be reconnected. Enter new credentials (mydomain.com/labuser).


