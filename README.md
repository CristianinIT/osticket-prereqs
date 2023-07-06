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

- Enable Internet Information Services (IIS)
- Install web platform installer
- Install MySQL
- Install C++ redistributable

<h2>Installation Steps</h2>

To start the tutorial we will create a virtual machine (VM) using Microsoft Azure. The VM's name can be anything you decide to use, however the recommended specifications for the VM should include windows 10 and at least 2 vcpu. These choices will allow the VM to run smoothly. The last step is to write down a username and password that you will use for logging into the VM after it's ready to be used.

<p>
<img <img width="721" alt="image" src="https://github.com/CristianinIT/osticket-prereqs/assets/138620922/e5e7ac82-1450-4509-9217-61004ab3664e">

</p>
<p>
The next step is connecting to the VM using Remote Desktop Protocol (RDP). Use the VM's public IPv4 address found in the VM's overview section and connect to it.
</p>
<br />

<p>
<img <img width="721" alt="image" src="https://github.com/CristianinIT/osticket-prereqs/assets/138620922/59ce92c3-e1bd-4f18-ba3d-3c111ef1ab09">

</p>
<p>
Once the VM is up and running, downlaod the necessary files through the VM. https://drive.google.com/drive/u/0/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6
Next, install and enable Internet Information Services (IIS) and CGI via control panel. While in control panel click the following:
  - Uninstall or change a program
  - Turn Windows features on or off
  - Expand IIS, World Wide Web Services, Application Development Features
  - Enable CGI
  
</p>
<br />

<p>
<img <img width="721" alt="image" src="https://github.com/CristianinIT/osticket-prereqs/assets/138620922/abe01a5f-57ec-4e2f-96b9-76cb6731723b">

<p>
Once those changes are applied the next step is to downlaod and install PHP Manager for IIS and rewrite module within the VM. After completing those create a directory for PHP on the local hard drive.
</p>
<br />

<p>
<img <img width="721" alt="image" src="https://github.com/CristianinIT/osticket-prereqs/assets/138620922/dcbf8877-750c-4820-8b13-a75637db593b">

</p>
<p>
Next, download php-7.3.8 file and extract the files to the PHP folder. Once that is done download the VC_redist and MySQL-5.5.62 files.
  
</p>
<br />

<p>
<img <img width="721" alt="image" src="https://github.com/CristianinIT/osticket-prereqs/assets/138620922/ddaf0dd3-7b25-43e2-8f47-7ca649b71337">

<p>
Once MySQL is installed, a password must be created.
  
</p>
<br />

<p>
<img <img width="721" alt="image" src="https://github.com/CristianinIT/osticket-prereqs/assets/138620922/261ce44a-579e-45cf-a169-feb02b152e12">

<p>
Now, we will open IIS and right click to run as administrator. Open PHP Manager and register a new PHP version which will be in the PHP folder under "php-cgi.exe". Make sure to restart the IIS.
</p>
<br />

<p>
<img <img width="946" alt="image" src="https://github.com/CristianinIT/osticket-prereqs/assets/138620922/7c32f535-30ab-4a8d-9859-5d659946545a">

<p>
Download the osTicket file, extract and "upload" the folder to c:\inetpub\wwwroot by moving the "upload" folder into the designated folder. After that rename the "upload" folder to "osTicket". Open IIS, click stop and restart the server. In IIS, select the following; Sites, Default, osTicket and on the right click "Browse*8:80".
</p>

<p>
<img <img width="946" alt="image" src="https://github.com/CristianinIT/osticket-prereqs/assets/138620922/10d1c789-89e0-4184-b324-2db13b592824">
<p>
<img <img width="946" alt="image" src="https://github.com/CristianinIT/osticket-prereqs/assets/138620922/2284aec4-8907-42cd-88bb-83ac6586539d">

<p>
The osTicket installer page will pop up but some extensions will need to be enabled. Go to IIS, click on the following: Sites, Default, osTicket. Double click PHP Manager and click on "Enable or disable an extension". Enable php_imap.dll, php_intl.dll, php_opcache.dll.
</p>

<p>
<img <img width="721" alt="image" src="https://github.com/CristianinIT/osticket-prereqs/assets/138620922/393f356c-bfaf-4e1a-812c-bca3027e94dd">
<p>
<img <img width="946" alt="image" src="https://github.com/CristianinIT/osticket-prereqs/assets/138620922/8c62cbf6-d9e8-42a7-9156-c1d7aa0c5e16">

<p>
Refresh the osTicket installer page. From here, go to C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php and rename "ost-sampleconfig.php" to "ost-config.php". Right click the file and disable inheritance via security's advance settings. Add permissions for everyone to have full control.
</p>

<p>
<img <img width="721" alt="image" src="https://github.com/CristianinIT/osticket-prereqs/assets/138620922/37a1920d-4442-4e9b-8e1e-a28927a91e4f">
<p>
<img <img width="721" alt="image" src="https://github.com/CristianinIT/osticket-prereqs/assets/138620922/a3a04994-7726-4aa5-a4a8-116750aa531d">
<p>
<img <img width="721" alt="image" src="https://github.com/CristianinIT/osticket-prereqs/assets/138620922/9636b1d1-0c33-49ad-99d4-d28312a8af88">

<p>
Go to the osTicket page and begin setting up the required information. Once that is completed, download and install HeidiSQL, type in the password that was used for MySQL. In HeidiSQL, right click "unamed" and create a new database and name it "osticket". 
</p>

<p>
<img <img width="721" alt="image" src="https://github.com/CristianinIT/osticket-prereqs/assets/138620922/fd6a34f5-e43e-4339-9a68-2fd7b9050622">
<p>
<img <img width="721" alt="image" src="https://github.com/CristianinIT/osticket-prereqs/assets/138620922/cc4f511e-00f4-411e-a927-d3f98dfa3eec">

<p>
Go back to the osTicket installer page and fill out the database settings to finalize. Click "Install Now" and congrats on succesfully installing osTicket. Ensure on deleting the setup folder in C:\inetpub\osTicket. Also, set permessions tp "Read" only for the "ost-config.php" folder via security's advanced settings. Now, osTicket is ready to be used.
</p>
<p>
<img <img width="721" alt="image" src="https://github.com/CristianinIT/osticket-prereqs/assets/138620922/c2e09c0b-add7-4b9f-a9fb-06f1a3e5d7a0">
<p>
<img <img width="721" alt="image" src="https://github.com/CristianinIT/osticket-prereqs/assets/138620922/f7143de9-8c1a-4de8-b504-8dfa9759d4b6">
