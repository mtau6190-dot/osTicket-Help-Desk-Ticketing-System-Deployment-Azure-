<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket: Help Desk Ticketing System Deployment (Azure)</h1>
In this project, I set up and configured the osTicket help desk ticketing system within my Azure lab environment. The setup phase focused on building the technical foundation: creating a Windows 11 virtual machine, installing and enabling IIS with CGI support, configuring PHP and MySQL, and deploying the osTicket application files into the web root. I then prepared the configuration file, established database connectivity, and completed the browser-based installation. This phase ensured osTicket was fully operational and ready for further customization and use.<br />


<h2>Environments and Technologies Used</h2>

- Languages/Tools: IIS, MySQL, PHP
- Environments: Azure Virtual Machines
- Technologies/Services: IIS (Internet Information Services), MySQL, PHP, osTicket application

<h2>Operating Systems Used </h2>

- Windows 11 Pro</b>

<h2>High-Level Deployment Steps</h2>

- Step 1: osTicket Setup
- 1.1: Created a VM
- 1.2: Preapared Installation Files
- 1.3: Installed IIS and CGI
- 1.4: Installed Dependencies
- 1.5: Configure IIS & PHP
- 1.6: Deployed osTicket Application
- 1.7: Configured osTicket
- 1.8: Database Setup
- 1.9: Successfully Installed osTicket with their URLs for the Admins and End-Users

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

<h3>1.5 - Configured IIS & PHP</h3>
<img width="1173" height="485" alt="image" src="https://github.com/user-attachments/assets/fb9ea7b1-a43a-47b2-b906-9eccad430538" />
<p>Registered C:\PHP\php-cgi.exe in IIS to tell the web server how to process PHP files. This step connects IIS to the PHP engine, so it can run osTicket’s scripts. Restarted IIS afterward reloads the server with this new configuration, ensuring PHP is active and ready to serve osTicket pages. Without this, PHP won’t execute and the site won’t work.
</p>

<h3>1.6 - Deployed osTicket</h3>
<img width="1416" height="380" alt="image" src="https://github.com/user-attachments/assets/84d060dc-b212-4a49-be9d-754a5750beac" />
<img width="503" height="337" alt="image" src="https://github.com/user-attachments/assets/3f731bfd-0ef8-4ab0-b478-ed70c302bc79" />
<img width="1706" height="521" alt="image" src="https://github.com/user-attachments/assets/721b3ca1-fc40-4bb7-9053-8f1497f32e98" />

<p>From the osTicket installation folder, unzipped "osTicket-v1.15.8.zip" and copied the "Upload" folder into "c:\inetpub\wwwroot". Then within the folder, I renamed the "upload" folder to "osTicket".
This step prepares osTicket for installation and public access through IIS. In IIS → Sites → Default → osTicket → click *Browse :80 to open in browser. This confirms that osTicket is successfully hosted on my IIS web server and ready for browser-based installation. By browsing to http://localhost/osTicket/setup/, I launched the installer, which checked prerequisites and guided me through final configuration. This step proves my IIS, PHP, and file setup are working.</p>

<h3>1.7 - Configured osTicket</h3>
<img width="1030" height="597" alt="image" src="https://github.com/user-attachments/assets/70cc7f62-d1ed-4d9b-8caf-cd8f5fca47b7" />
<img width="833" height="557" alt="image" src="https://github.com/user-attachments/assets/b9a512c2-b95a-4b27-b4a0-272e73f886ad" />
<img width="1580" height="756" alt="image" src="https://github.com/user-attachments/assets/53234072-a7b8-4824-b928-cbb9356e0d3b" />

<P>I renamed ost-sampleconfig.php to ost-config.php because osTicket needs an active configuration file to store its settings. Permissions are temporarily set to Full Control so the installer can write those settings during setup. In the browser, naming your helpdesk and setting a default email establishes its identity and ensures customer requests can be received and converted into tickets. These steps finalize installation and make osTicket functional.</P>

<h3>1.8 - Database Setup</h3>
<img width="693" height="565" alt="image" src="https://github.com/user-attachments/assets/62c21ac7-36cf-4618-8c46-4e22d287b632" />
<img width="1188" height="716" alt="image" src="https://github.com/user-attachments/assets/a360802e-2561-475e-88cb-342af9c6aea7" />
<p>I installed HeidiSQL to manage the MySQL database easily. By creating a session with the root/root credentials and then making a database called osTicket, I prepared the storage backend where all ticket data, users, and system settings will be saved. This database is what osTicket connects to during installation so it can function properly.</p>

<h3>1.9 - Successfully Installed osTicket with their URLs for the Admins and Users</h3>
<img width="1807" height="887" alt="image" src="https://github.com/user-attachments/assets/97a8b639-3842-40b5-b654-c837e5acc106" />
<img width="604" height="167" alt="image" src="https://github.com/user-attachments/assets/77651994-91ff-4d33-85d9-06e8131916d2" />
<img width="1807" height="881" alt="image" src="https://github.com/user-attachments/assets/ec11f0bc-6e61-4ced-ba59-db51a2e38c95" />
<img width="1816" height="616" alt="image" src="https://github.com/user-attachments/assets/29b3e48a-d8d6-419c-b0ac-cb6df9c462ee" />
<P>The above image confirms that osTicket is fully installed and operational. I successfully logged in as an admin, viewed the ticket dashboard at localhost/osTicket/scp/index.php. The default ticket “osTicket Installed!” showed the system is working, ready to receive and manage support requests.</P>

<h2>osTicket Setup Outcome Summary:</h2>

I successfully deployed osTicket on a Windows 11 VM in Azure, built a complete web-based help desk system from scratch. I installed and configured IIS, PHP, MySQL, and essential modules, then registered PHP with IIS and restarted the server to activate changes. I extracted osTicket files into the web root, renamed the folder for clean URL access, and launched the browser-based installer. I then renamed and configured the ost-config.php file with proper permissions, created a MySQL database using HeidiSQL, and completed the installation through the web interface.












