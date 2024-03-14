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
1.) The first thing you should do is create a virtual machine by going to https://portal.azure.com/. Set up your virtual machine with Windows 10 Pro, version 22H2. You will want to create a virtual machine with at least 2 vCPUs and 16 GiB of memory.
2.) Once you have created your virtual machine, you will want to connect to it by using the public IP address the VM is set with. You will connect using the remote desktop connection app.
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
3.) Once you have connected to your virtual machine, you will want to go to your control panel. From the control panel, open programs. Select Turn Windows features on and off.

4.) You will want to install/enable IIS in Windows with CGI and Common HTTP Features
•	World Wide Web Services -> Application Development Features -> [X] CGI [X] Common HTTP Features

•	NOTE: Make sure all Common HTTP Features are checked.
•	To ensure the IIS is installed/enabled, go to a browser of your choice and search for 127.0.0.1. It should look something like this.
</p>
<br />

<p>
<img src="https://i.imgur.com/RTxZZZf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
5.) Now that IIS is enabled download and install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi) from the installation files. Then, go through the install wizard and complete the installation.

  6.) Next, from the Installation Files, download and install the Rewrite Module (rewrite_amd64_en-US.msi)

7.) Create a folder in the C drive called PHP.

8.) From the Installation Files, download PHP 7.3.8 (php-7.3.88-nts-Win32-VC15-x866.zip) and unzip the contents into C:\PHP

!! ATTENTION!! If this appears, choose to “Keep” the file:

</p>
<br />
</p>
<img src="https://i.imgur.com/RTxZZZf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<p>
9.) Once you have downloaded and extracted the zip file into the PHP folder on the C drive, download and install the VC_redist.x86.exe from the installation files. Go through the setup wizard to finish setting up and installing the VC_redist.x86.exe.

  10.) Download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi) Run the setup wizard: Typical Setup -> Launch Configuration Wizard (after install) -> Standard Configuration ->

Make the new root password: Password1.
<p>
  <img src="https://i.imgur.com/RTxZZZf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
11.) Now that we have the files downloaded and installed, we will want to search for IIS in the Windows search bar. Open IIS as an administrator. The program should look like this.
<p>
  12.) We will now want to register PHP from within IIS. Click on PHP Manager
</p>
You will want to provide a path to the php executable file (php-cgi.exe)). Go to C Drive -> PHP -> click on php-cgi file.

<p>
  Restart the IIS server.
  <p>
  13.) Install osTicket v1.15.8 -Download osTicket from the Installation Files Folder -Extract and copy "upload" folder to c:\inetpub\wwwroot -Within c:\inetpub\root, Rename "upload" to "osTicket.”
Reload IIS again.

    14.) On IIS go to sites -> Default -> osTicket -On the right, click “Browse *:80.”
  
  </p>
  Some extensions are not enabled on the osTicket browser.
</p>
To enable the extensions: -Go back to IIS, sites -> Default -> osTicket -Double click PHP manager -Click "Enable or disable an extension."
<p>
We will want to enable three extensions from here.
1.) php_imap.dll

  2.) php_intl.dll

3.) php_opcache.dll
<p>
  <img src="https://imgur.com/g6Q9K1d.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
 15.) Once those extensions are enabled in IIS, we want to rename one of the files in our osTicket folder. Go into the file explorer and search for C;\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php

We are going to rename the ost-sampleconfig.php to ost-config.php

Now that we have renamed the files, right-click on the file and go to properties. From there, click security, click on advance, and turn off the inheritance. We will select Remove all inherited permissions from this object.

Now, we will add new permissions.

Click Add
 
</p>
Select a principal.
<p>
  
</p>
Type "Everyone" in the box.
<p>
  
</p>
Click Apply and OK.
<p>
 Once that is done, we will continue to set up osTicket in the browser. Click Continue on the osTicket browser page. Fill out the page as required, except for the Database Settings at the bottom. We will get to that.

  We will want to download and install HeidiSQL from the Installation Files.
  <p>
    
  </p>

When the program is open, we will create a new session.
<p>
  
</p>

We want to ensure the username is root and the password is Password1.
 
</p>
Once connected to the session, we will return to the browser to finish setting everything up. Under the Database Settings in the browser, the username will be root, and the password will be Password1.

We will now create a new database within HeidiSQL. In Heidi, right-click on the left side where it says "Unnamed," select "Create new," and then select "Database." Name the new database osTicket. Once we have the latest database set up, go back to the osTicket browser and type in osTicket under MySQL Database.
<p>
The last step is to clean up. We will want to delete the setup folder in our system. -Delete: C:\inetpub\wwwroot\osTicket\setup Only delete the setup folder and nothing else.

  We then will want to set the permissions back to "Read" only in the ost-config.php file.
  
</p>
The last step after that is to log in to osTicket on the browser.
<p>
  
</p>
Congrats! You have now successfully installed and set up osTicket!

