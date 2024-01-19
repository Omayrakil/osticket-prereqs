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

- Item 1
- Item 2
- Item 3
  


<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/TiTdWSn.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
The first step is to sign in to the Azure Portal and create a resource group. After the resource group is created, we are going to create a virtual machine(VM) on Azure that will serve as our hosting evironment. step three is to choose the desired version of Ubuntu Server and click on create. Provide the required details such as resource group,virtual machine name,and password.Select the appropriate size for the virtual machine based on the requirement. Configure the networking options,such as virtual network and subnet. the last step is to review the settings and click on "create" to create the virtual machine.
</p>
<br />

<p>
<img src="https://i.imgur.com/qj9tauk.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Once the virtual machine is created, we are going to connect our virtual machine to the remote destop by using our VM ip address,the username and paasword that we use to create our Virtual machine.After connecting to virtual machine, we can now proceed with the istallation of osTicket by following the steps for a regular installation on a linux server.
</p>
<br />

<p>
<img src="https://i.imgur.com/RTxZZZf.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
</p>
<p>
Next step we are going to Install/Enable IIS(Internet Information Services) in Windows with CGI and Common HTTP Features
  -World Wide Web Services -Application Developement Features- 
  [X]CGI,
  [X]Common HTTP Features, AND IIS Management Console
  - Internet Information Services- Web Management Tools -IIS Management Console.
  [X]IIS Management Console. After we are done installing the IIS we are going to check if the installation was successful by opening a new browser and type 127.0.0.1 to see if is working, but if the istallation does not work for the first time we can inunstall just by unchecking the IIS and repeat the same process.
</p>
<br />
