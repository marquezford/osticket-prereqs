<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://www.youtube.com)

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Create a Resource Group
- Create an Azure Virtual Machine Windows 10, 4 vCPUs
- Name: Vm-osticket
- Create a username (To RDP into the VM)
- Create a password (To RDP into the VM)

<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/1U0L2m0.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
   -Install / Enable IIS in Windows WITH CGI
   <br />
    -Right click on the start menu
   <br />
    -Click Run
   <br />
    -Type control for control Panel 
   <br />
    -Click programs
   <br />
    -Select turn windows features on or off
   <br />
    -Go to internet information services (Check it to turn it on)
   <br />
    -Expand it & Expand World Wide Web Services
   <br />
    -Expand application developer
   <br />
    -Check CGI & click ok
</p>
<br />

<p>
<img src="https://i.imgur.com/4ze2sSv.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Check the box next to CGI and click ok.
</p>
<br />

<p>
<img src="https://i.imgur.com/9qZ94sL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Test if your web server is working. Open a new tab and try to run a webpage off yourself by typing 127.0.0.1(Local Host or Loopback) in the address bar.
</p>
<br />

<p>
<img src="https://i.imgur.com/dOQOrnY.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Download and Install PHP Manager for IIS.
</p>
<br />

<p>
<img src="https://i.imgur.com/qgs66m3.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Download and Install the Rewrite Module.
</p>
<br />

<p>
<img src="https://i.imgur.com/CD8ogxy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Creat a directory for PHP on the local hard drive.
</p>
<br />

<p>
<img src="https://i.imgur.com/5MqPGla.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next download PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip).
</p>
<br />

<p>
<img src="https://i.imgur.com/Tih02KP.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Unzip the PHP contents into the PHP directory that you've just created.
</p>
<br />

<p>
<img src="https://i.imgur.com/WG8lpSb.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Download and Install C++ Redistributable (VC redist x86.exe).
</p>
<br />

<p>
<img src="https://i.imgur.com/fZJ1GOy.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 - Download and Install MySQL 5.5.62 (mysql-5.5.62-win32.msi).
   <br />
 - Click Typical Install & Install
   <br />
 - Make sure Launch The MySQL Instance Configuration Wizard is checked & click finish.
   <br />
 - Setup your credentials ( Open a notepad and save it where you can find it later).
   <br />
   - Select standard Configuration, Click next, Set Password & user will be root.
   <br />
   - Leave everything else as is and Execute.
   <br />
</p>
<br />

<p>
<img src="https://i.imgur.com/qpyk3rv.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
 - Click Start, Search IIS, Right Click it & Run as Admin.
   <br />
 - Register PHP in IIS (Select New PHP Version). 
   <br />
 - Browse for the PHP Directory That Was Created Earlier.
   <br />
 - Click on PHP Directory, Select php-cgi & Click open, Click ok.
   <br />
 - Restart the Web Server (Click vm-osticket Under Connections to the Left & Hit Restart on the Right Under Manage Server).
   <br />
</p>
<br />

<p>
<img src="https://i.imgur.com/eZiCA0E.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
-Time to Download & Install osTicket
   <br />
   - Download osTicket v1.15.8
   <br />
   - Extract & Copy "upload" folder to c:\inetpub\wwwroot
   <br />
   - Within the c:\inetpub\wwwroot, Rename the "upload" folder to "osTicket"
   <br />
</p>
<br />

<p>
<img src="https://i.imgur.com/W1bhx23.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
- Reload IIS (Restart).
   <br />
 - Go to sites -> Default -> osTicket (On the Right, Click "Browse *:80") & You Should See osTicket page.
   <br />
</p>
<br />

<p>
<img src="https://i.imgur.com/WWUjaBt.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
- Time to Install The Recommended Extentions For osTicket
   <br />
   - Go to IIS, Sites -> Default -> osTicket
   <br />
   - Double-Click PHP Manager
   <br />
   - Click "Enable or Disable an Extension"
   <br />
     - Enable: php_imap.dll
   <br />
     - Enable: php_intl.dll
   <br />
     - Enable: php_opcache.dll
   <br />
</p>
<br />

<p>
<img src="https://i.imgur.com/6Gqx8rj.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
- Refresh the osTicket Site in Your Browser & Observe the Changes.
</p>
<br />

<p>
<img src="https://i.imgur.com/v8uy4Mr.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
- Rename: ost-config.php
   - From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
   <br />
   - To: C:\inetpub\wwwroot\osTicket\include\ost-config.php
   <br />
- Assign Permissions: ost-config.php 
   <br />
   - Right Click ost-config.php
   <br />
   - Click Properties
   <br />
   - Security & Click Advanced
   <br />
   - Disable Inheritance
   <br />
   - Remove all permissions
   <br />
   - Add Permissions
   <br />
   - Select Principal, Put Everyone, and Check Names
   <br />
   - Select Full Control, Hit ok, Apply & Click ok
   <br />
</p>
<br />

<p>
<img src="https://i.imgur.com/kSoC0Jn.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
- Continue Setting Up osTicket in the Browser (Click Continue)
   <br />
   - Name Helpdesk
   <br />
   -Default Email (Receive Email From Customers)
   <br />
</p>
<br />

<p>
<img src="https://i.imgur.com/j3Pn75D.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
- Download & Install HeidiSQL
   <br />
- Open Heidi SQL
<br />
</p>
<br />

<p>
<img src="https://i.imgur.com/crD1OMI.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
   - Create a New Session, root/Password1
   <br />
   - Connect to the Session
   <br />
   - Create a Database Called "osTicket" & Click ok
   <br />
</p>
<br />

<p>
<img src="https://i.imgur.com/jEFW59c.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />

<p>
<img src="https://i.imgur.com/az8unEL.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Lorem ipsum dolor sit amet, consectetur adipiscing elit, sed do eiusmod tempor incididunt ut labore et dolore magna aliqua. Ut enim ad minim veniam, quis nostrud exercitation ullamco laboris nisi ut aliquip ex ea commodo consequat. Duis aute irure dolor in reprehenderit in voluptate velit esse cillum dolore eu fugiat nulla pariatur.
</p>
<br />
