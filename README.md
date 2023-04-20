<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>
<br />
<br />

<h2>Technologies and Environments Used<a><h2/>

- Azure Virtual Machines
- PHP Manager
- MySQL
- osTicket (Help Desk Ticketing System)


<h2>In this tutorial I will install osTicket on an Azure VM (Virtual Machine). This tutorial assumes you have already created a VM and are logged in to it. The install files for osTicket can be found <a href= https://drive.google.com/drive/u/1/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6 /> here <a><h2/>

<p align="center">
<img src="https://photos.google.com/share/AF1QipOPz8yFl0zOqsWRbEkhoagbe_VbRZG93pIxs1zE9AaBaCPASMaRD69acC01lXGPfA?key=YXBOMFhIN045SFdScTNabndydGg3d2RpaVgtS3Jn alt="osTicket Installation"/>
</p>
<br />
<br />

Step 1. Install / Enable IIS in Windows WITH CGI (World Wide Web Services -> Application Development Features -> [X] CGI)

<p align="center">
<img src="https://imgur.com/TLFqV00.png alt="Traffic Examination"/>
</p>
<br />
<br />

Step 2. From the installation files, install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi)

<p align="center">
<img src="https://imgur.com/hX8SZyK.png alt="Traffic Examination"/>
</p>
<br />
<br />

Step 3. From the installation files, install the Rewrite Module (rewrite_amd64_en-US.msi)

<p align="center">
<img src="https://imgur.com/zGzCaig.png alt="Traffic Examination"/>
</p>
<br />
<br />

Step 4. Create the directory C:\PHP

<p align="center">
<img src="https://imgur.com/70SOSrg.png alt="Traffic Examination"/>
</p>
<br />
<br />

Step 5. From the installation files unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into C:\PHP

<p align="center">
<img src="https://imgur.com/bJ4SjBM.png alt="Traffic Examination"/>
</p>
<br />
<br />

Step 6. From the installation files install VC_redist.x86.exe.

<p align="center">
<img src="https://imgur.com/bsCwU9j.png alt="Traffic Examination"/>
</p>
<br />
<br />


Step 7. From the installation files install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
 - Typical Setup ->
 - Launch Configuration Wizard (after install) ->
 - Standard Configuration ->
 - Password1

<p align="center">
<img src="https://imgur.com/1rBQpJ2.png alt="Traffic Examination"/>
</p>
<br />
<br />

7b.
<p align="center">
<img src="https://imgur.com/NQInyxj.png alt="Traffic Examination"/>
</p>
<br />
<br />

7c.
<p align="center">
<img src="https://imgur.com/qBAMYl6.png alt="Traffic Examination"/>
</p>
<br />
<br />

Step 8. Open IIS as an Admin, register PHP, then restart the server 


<p align="center">
<img src="https://imgur.com/Wyz1cHU.png alt="Traffic Examination"/>
</p>
<br />
<br />

8b.
<p align="center">
<img src="https://imgur.com/xUuPB6u.png alt="Traffic Examination"/>
</p>
<br />
<br />

8c.
<p align="center">
<img src="https://imgur.com/ASXOKyF.png alt="Traffic Examination"/>
</p>
<br />
<br />

8d.
<p align="center">
<img src="https://imgur.com/GLi5Pqf.png alt="Traffic Examination"/>
</p>
<br />
<br />

Step 9. Install osTicket v1.15.8


<p align="center">
<img src="https://imgur.com/GBdqll4.png alt="Traffic Examination"/>
</p>
<br />
<br />

9b. Copy “upload” folder to c:\inetpub\wwwroot
<p align="center">
<img src="https://imgur.com/4jdRjRF.png alt="Traffic Examination"/>
</p>
<br />
<br />

9c. Within C:\inetpub\wwwroot, rename “upload” to “osTicket”
<p align="center">
<img src="https://imgur.com/772EfbX.png alt="Traffic Examination"/>
</p>
<br />
<br />

Step 10. Note that some extensions are not enabled
 
Go back to IIS, sites -> Default -> osTicket and double click PHP manager

<p align="center">
<img src="https://imgur.com/9bPE4OV.png alt="Traffic Examination"/>
</p>
<br />
<br />

10b. Click “Enable or disable an extension” and enable these extensions: php_imap.dll, php_intl.dll, php_opcache.dll

<p align="center">
<img src="https://imgur.com/sKw7cTW.png alt="Traffic Examination"/>
</p>
<br />
<br />

10c. Install the three .dll extensions as shown below

<p align="center">
<img src="https://imgur.com/UeF0kNg.png alt="Traffic Examination"/>
</p>
<br />
<br />

Step 11. After navigating to http://localhost/osTicket/setup/install, rename the ost-config.php file (see below) and click continue.

- From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
- To: C:\inetpub\wwwroot\osTicket\include\ost-config.php

<p align="center">
<img src="https://imgur.com/D1ABrGV.png alt="Traffic Examination"/>
</p>
<br />
<br />

Step 12. After changing the ost-config.php file and clicking continue and you should see the following  screen:

<p align="center">
<img src="https://imgur.com/bklUu4d.png alt="Traffic Examination"/>
</p>

Once the above information is filled in click save changes at the bottom of the screen.
<br />
<br />

12b. After saving you should see this screen. Click continue at the bottom of the screen.

<p align="center">
<img src="https://imgur.com/ZLDvqlg.png alt="Traffic Examination"/>
</p>
<br />
<br />

Step 13. Back in osTicket Click the Dashboard tab and you should see the following screen:

<p align="center">
<img src="https://imgur.com/T7vYSS5.png alt="Traffic Examination"/>
</p>
<br />
<br />

Step 14. From the installation files install HeidiSQL

- Open Heidi SQL
- Create a new session, root/Password1
- Connect to the session
- Create a database called “osTicket”
- Click Open

<p align="center">
<img src="https://imgur.com/Xwg85Fr.png alt="Traffic Examination"/>
</p>
<br />
<br />

14b. After you click open you should see the following screen:

<p align="center">
<img src="https://imgur.com/AlvSYKt.png alt="Traffic Examination"/>
</p>
<br />
<br />

Success! You have installed osTicket!
Thank You for reading!

For the the next tutorial in this series go <a href=https://github.com/presicion25/osTicket-Configuration>here</a></h2>
