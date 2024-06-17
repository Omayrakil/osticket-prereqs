<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Azure Virtual Machine
- Internet Information Services (IIS)
- PHP Manager
- Rewrite Module
- VC Redist
- MySQL
- Heidi SQL
- osTicket v1.15.8
- Link to downloads: https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6
  


<h2>Installation Steps</h2>

</p>
<p>
1.) First, I create a virtual machine at https://portal.azure.com/. Set up your virtual machine with Windows 10 Pro, version 22H2. You will want to create a virtual machine with at least 2 vCPUs and 16 GiB of memory.
2.) Once you have created your virtual machine, you will want to connect to it using the public IP address the VM is set with. You will connect using the remote desktop connection app.
<p>
<img src="https://i.imgur.com/TiTdWSn.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>

</p>
<br />

<p>
  
<img src="https://i.imgur.com/qj9tauk.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
3.) Once connected to your virtual machine, you must go to your control panel. From the control panel, open programs. Select Turn Windows features on and off.

4.) You will want to install/enable IIS in Windows with CGI and Common HTTP Features
•	World Wide Web Services -> Application Development Features -> 

[X] CGI

[X] Common HTTP Features

•	NOTE: Make sure all Common HTTP Features are checked.
•	To ensure the IIS is installed/enabled, go to a browser of your choice and search for 127.0.0.1. It should look something like this.
</p>
<br />

<p>
<img src="https://i.imgur.com/RTxZZZf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
5.) Now that IIS is enabled, download and install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi) from the installation files. Then, go through the install wizard and complete the installation.

  6.) Next, from the Installation Files, download and install the Rewrite Module (rewrite_amd64_en-US.msi)

7.) Create a folder in the C drive called PHP.

8.) From the Installation Files, download PHP 7.3.8 (php-7.3.88-nts-Win32-VC15-x866.zip) and unzip the contents into C:\PHP

</p>
<p>
9.) Once you have downloaded and extracted the zip file into the PHP folder on the C drive, download and install the VC_redist.x86.exe from the installation files. You can go through the setup wizard to finish setting up and installing the VC_redist.x86.exe.

  10.) Download and install MySQL 5.5.62 (MySQL-5.5.62-win32.msi). Run the setup wizard: 
  
  ->Typical Setup 
  
  -> Launch Configuration Wizard (after installation) 
  
  -> Standard Configuration 
 
  -> Make up a password for root that you can remember
<p>
 

  <img src="https://imgur.com/yfQ9eYE.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
11.) Now that we have the files downloaded and installed, we will want to search for IIS in the Windows search bar. 

Open IIS as an administrator. 

The program should look like this.
<p>
 <img src="https://imgur.com/9zAZs5p.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>


<p>
  12.) We will now want to register PHP from within IIS. Click on PHP Manager
</p>
You will want to provide a path to the PHP executable file (php-cgi.exe)).

-> Go to C Drive 

-> PHP 

-> Click on php-cgi file.

<p>
  Restart the IIS server.
  <p>
  13.) Install osTicket v1.15.8 
    
    -Download osTicket from the Installation Files Folder 
    
    -Extract and copy to "upload" folder to c:\inetpub\wwwroot 
    
    -Within c:\inetpub\root, Rename "upload" to "osTicket.”


Reload IIS again.

    14.) On IIS, go to sites -> Default -> osTicket 
    
    -On the right, click “Browse *:80.”
   
  <img src="https://imgur.com/wTmjlUi.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
   
   </p>
  Some extensions are not enabled on the osTicket browser.
  
  <img src="https://imgur.com/pgpyjmV.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
To enable the extensions: 

-Go back to IIS, sites -> Default -> osTicket 

-Double click PHP manager 

-Click "Enable or disable an extension."
<p>
We will want to enable three extensions from here.

  1.) php_imap.dll

  2.) php_intl.dll

3.) php_opcache.dll

 <img src="https://imgur.com/6yrk6kv.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<p>
  <img src="https://imgur.com/g6Q9K1d.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
 15.) Once those extensions are enabled in IIS, we want to rename one of the files in our osTicket folder. 
 
 Rename: ost-config.php
 
 From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php

We are going to rename the ost-sampleconfig.php to ost-config.php

Now that we have renamed the files 

-> Right-click on the file and go to properties. 

->From there, click Security->Advance->Disable Inheritance->Remove all inherited permissions from this object

->And Add New Permissions

->Security->Advanced->Add->Select a principal->Everyone->Full control->Apply->OK

</p>

<p>
 Once that is done, we will continue to set up osTicket in the browser. Click Continue on the osTicket browser page. Fill out the page as required, except for the Database Settings at the bottom. 

  We will want to download and install HeidiSQL from the Installation Files.
  <p>
     <img src="https://imgur.com/AQqr5ge.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
  </p>

When the program is open, we will create a new session.
<p>
  
</p>

We want to ensure the username is root and the password we created.
 
</p>
Once connected to the session, we will return to the browser to finish setting everything up. Under the Database Settings in the browser, the username will be root, and the password will be the password we created.

We will now create a new database within HeidiSQL. In Heidi, 

-> Right-click on the left side where it says "Unnamed," 

-> Select "Create new," and then select "Database." 

->Name the new database osTicket. 
<img src="https://imgur.com/JZGumAd.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

->Once we have the latest database set up, go back to the osTicket browser and type in osTicket under MySQL Database.

<img src="https://imgur.com/AI36ttf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<p>
  <img src="https://imgur.com/SFXeBHi.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

  ->Browse to the help desk login page:http://localhost/osTicket/scp/login.php
 
  <img src="https://imgur.com/rHyZuen.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

  <img src="https://imgur.com/MRmluNq.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

  Congrats! You have now successfully installed and set up osTicket!
  

  End Users osTickets URL

    -http://localhost/osTicket/ 
 
  
  The last step is to clean up. We will want to delete the setup folder in our system. 
 
  -Delete: C:\inetpub\wwwroot\osTicket\setup Only delete the setup folder and nothing else.

  -We then will want to set the permissions back to "Read" only in the ost-config.php file.
  <img src="https://imgur.com/6dccsRF.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>

