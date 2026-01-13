<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket: Help Desk Ticketing System Deployment (Azure)</h1>
In this project, I managed to set up and configure the osTicket help desk ticketing system inside my Azure lab environment. The goal was to demonstrate how IT teams manage support requests, streamline workflows, and enforce accountability using a centralized ticketing platform.<br />


<h2>Environments and Technologies Used</h2>

- Languages/Tools: PowerShell, CMD, IIS, MySQL, PHP
- Environments: Azure Virtual Machines, Windows Server 2022
- Technologies/Services: IIS (Internet Information Services), MySQL, PHP, osTicket application

<h2>Operating Systems Used </h2>

- Windows 11 Pro</b> (25H2)

<h2>High-Level Deployment Steps</h2>

- Step 1: osTicket Setup
- Item 2
- Item 3
- Item 4
- Item 5

<h2>Step 1: osTicket Setup</h2>
<h3>1.1 - Created a VM</h3>
<p>
<img width="606" height="240" alt="image" src="https://github.com/user-attachments/assets/cef71891-414a-459b-97bf-179e7f50ceb5" /><br>
<img width="1515" height="683" alt="image" src="https://github.com/user-attachments/assets/373c3314-d01b-4d46-b1ce-1b4227498a35" />

In Azure, I first created a Windows 11 VM and named it "osTicket-VM". I then
logged into the VM via Remote Desktop.</p>

<h3>1.2 - Prepared Installation Files</h3>
<p>
<img width="1113" height="594" alt="image" src="https://github.com/user-attachments/assets/22d952c1-30d3-46a6-8c5f-9166f416c0b8" />
<img width="1081" height="571" alt="image" src="https://github.com/user-attachments/assets/99ed9b04-49d7-4c7c-90a9-b6fe65440391" />
Downloaded osTicket-Installation-Files.zip into the VM.<br>
Unzipped it to the desktop → folder was named osTicket-Installation-Files<br>
This folder contained all the dependencies I needed (PHP, MySQL, IIS modules, etc.).<br>
