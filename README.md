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

<h3>1.3 - Installed IIS & CGI</h3>
<p>
<img width="817" height="553" alt="image" src="https://github.com/user-attachments/assets/0f46a18b-3878-41f4-bf64-5167178cf59d" /><br>
I successfully enabled Internet Information Services (IIS) with the CGI feature on my Windows VM. This is a critical step for hosting osTicket, since CGI allows PHP scripts to run under IIS, enabling dynamic web functionality for the help desk system.</p>

<h3>1.4 - Installed Dependencies</h3>
<p>
<img width="620" height="507" alt="image" src="https://github.com/user-attachments/assets/a5f2edeb-404f-4487-968d-31807b87bdbd" />
<img width="612" height="478" alt="image" src="https://github.com/user-attachments/assets/e4394ea0-1683-4893-a299-29a2606cb962" />
<img width="822" height="685" alt="image" src="https://github.com/user-attachments/assets/03a86edd-60d6-42ba-8150-d225fbb47106" />
<img width="1292" height="673" alt="image" src="https://github.com/user-attachments/assets/fa3ee39b-bd5f-4b38-b98d-faa4cb4b1fda" />
<img width="600" height="367" alt="image" src="https://github.com/user-attachments/assets/5ba4785d-c2e5-4d58-85c0-58e5c833a9e3" />
<img width="615" height="481" alt="image" src="https://github.com/user-attachments/assets/a3d9b02a-1bc8-45f1-b2df-bda3558686eb" /><br>
  
Installed PHP Manager for IIS.<br>
Installed IIS Rewrite Module.<br>
Created directory C:\PHP.<br>
Extracted PHP 7.3.8 into C:\PHP.<br>
Installed VC_redist.x86.exe (runtime libraries).<br>
Installed MySQL 5.5.62 → choose Typical Setup<br>

Together, these form the web server + scripting + database stack that osTicket needs to operate. Successfully built the full backend for a help desk system.
</p>

<h3>1.4 - Configured IIS & PHP</h3>
<img width="1173" height="485" alt="image" src="https://github.com/user-attachments/assets/fb9ea7b1-a43a-47b2-b906-9eccad430538" />
<p>Registered C:\PHP\php-cgi.exe in IIS to tell the web server how to process PHP files. This step connects IIS to the PHP engine, so it can run osTicket’s scripts. Restarted IIS afterward reloads the server with this new configuration, ensuring PHP is active and ready to serve osTicket pages. Without this, PHP won’t execute and the site won’t work.
</p>

<h3>1.5 - Deployed osTicket</h3>
<img width="1416" height="380" alt="image" src="https://github.com/user-attachments/assets/84d060dc-b212-4a49-be9d-754a5750beac" />
<img width="503" height="337" alt="image" src="https://github.com/user-attachments/assets/3f731bfd-0ef8-4ab0-b478-ed70c302bc79" />

<p>From the osTicket installation folder, unzipped "osTicket-v1.15.8.zip" and copied the "Upload" folder into "c:\inetpub\wwwroot". Then within the folder, I renamed the "upload" folder to "osTicket".
This step prepares osTicket for installation and public access through IIS.</p>


