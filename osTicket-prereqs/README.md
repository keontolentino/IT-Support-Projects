<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (21H2)

<h2>List of Prerequisites</h2>

- Web Platform Installer
- Microsoft Visual C++
- PHPManagerForIIS_V1.5.0
- osTicket Installer
- HeidiSQL

<h2>Installation Steps</h2>

<p>Note: If you don't know how to create and connect to a Virtual Machine then follow my tutorial <a href="../azure-network-protocols/README.md"> here </a>

<p>Create resource group and virtual machine. Connect to the Virtual Machine(VM) via RDP> Install Web Platform Installer and open, then add MySQL 5.5 and All simple versions of x86 PHP until 7.3</p>
<img src="../images/osTicket/osticket1/Failed-install.png" height="80%" width="80%"> <br />

<p>Download and install Microsoft Visual C++, PHPManagerForIIS_V1.5.0 since it fails on the installation for web platform installer. </p>
<img src="../images/osTicket/osticket1/Installed-C-PHPIISV1.5.png" height="80%" width="80%"> <br />

<p>Download and install osTicket, then extract and copy the "upload" folder to "c:\inetpub\wwwroot> Within c:\inetpub\wwwroot". Rename "upload" folder to "osTicket" </p>
<img src="../images/osTicket/osticket1/osTicket-extract-copy-rename.png" height="80%" width="80%"> <br />

<p>Open IIS from start menu, click the restart button located on the right side. Go to "sites" folder, click "default web site", click osticket and click "browse 80" on the right side </p>
<img src="../images/osTicket/osticket1/IIS-restart-browser80.png" height="80%" width="80%"> <br />

<p>On the osTicket folder choose PHP Manager, click enable or disable an  extension at the bottom. Enable php_imap.dll, php_intl.dll, php_opcache.dll. Go back to browser, refresh the page, and you will see the Intl Extension be checked </p>
<br />

<p>Rename: ost-config.php from C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php to C:\inetpub\wwwroot\osTicket\include\ost-config.php </p>
<img src="../images/osTicket/osticket1/ost-config-rename" height="80%" width="80%"> <br />

<p>Assign permissions for ost-config.php, right click the file then go to properties and security tab -> click advanced -> choose Disable Inheritance -> select remove all -> click add -> select a principal
-> type everyone and check names -> check full control then select ok. Go back to the browser and click continue, fill in Helpdesk Name, Default email, Admin user.</p>
<br />

<p>Download and Install HeidiSQL -> open heidisql -> click New, choose a password and click open > right click the new session on the left -> select create new database and fill in the name.
Go back to the browser and fill in the MySQL Database with the new database previously created. Fill in the credentials used for database setup and click install now.</p>
<img src="../images/osTicket/osticket1/Installed-mysql-osticket.png" height="80%" width="80%"> <br />


<p>The last step is to delete C:\inetpub\wwwroot\osTicket\setup > Set Permissions to Read and read&execute only C:\inetpub\wwwroot\osTicket\include\ost-config.php</p>
<img src="../images/osTicket/osticket1/permissions-ost-config" height="80%" width="80%"> <br />