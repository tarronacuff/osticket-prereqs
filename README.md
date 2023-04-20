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


<h2>In this tutorial I will install osTicket on an Azure VM (Virtual Machine). This tutorial assumes you have already created a VM and are logged in to it.<br />

<p align="center">
<a href="https://imgur.com/DsO4SUt"><img src="https://i.imgur.com/DsO4SUt.jpg" title="source: imgur.com" /></a>
</p>
<br />
<br />

Step 1. Install / Enable IIS in Windows WITH CGI (World Wide Web Services -> Application Development Features -> [X] CGI)

<p align="center">
<a href="https://imgur.com/Q2Eotpc"><img src="https://i.imgur.com/Q2Eotpc.jpg" title="source: imgur.com" /></a>
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
<a href="https://imgur.com/qAp8t7y"><img src="https://i.imgur.com/qAp8t7y.jpg" title="source: imgur.com" /></a>
</p>
<br />
<br />

Step 4. Create the directory C:\PHP

<p align="center">
<a href="https://imgur.com/diTApDW"><img src="https://i.imgur.com/diTApDW.jpg" title="source: imgur.com" /></a>
</p>
<br />
<br />

Step 5. From the installation files unzip PHP 7.3.8 (php-7.3.8-nts-Win32-VC15-x86.zip) into C:\PHP

<p align="center">
<a href="https://imgur.com/3Uzvf1a"><img src="https://i.imgur.com/3Uzvf1a.jpg" title="source: imgur.com" /></a>
</p>
<br />
<br />

Step 6. From the installation files install VC_redist.x86.exe.

<p align="center">
<a href="https://imgur.com/SA3JNRF"><img src="https://i.imgur.com/SA3JNRF.jpg" title="source: imgur.com" /></a>
</p>
<br />
<br />


Step 7. From the installation files install MySQL 5.5.62 (mysql-5.5.62-win32.msi)
 - Typical Setup ->
 - Launch Configuration Wizard (after install) ->
 - Standard Configuration ->
 - Password1

<p align="center">
<a href="https://imgur.com/VjmHDwn"><img src="https://i.imgur.com/VjmHDwn.jpg" title="source: imgur.com" /></a>
</p>
<br />
<br />

7b.
<p align="center">
<a href="https://imgur.com/I6v8Y0Q"><img src="https://i.imgur.com/I6v8Y0Q.jpg" title="source: imgur.com" /></a>
</p>
<br />
<br />

7c.
<p align="center">
<a href="https://imgur.com/1sH1wEu"><img src="https://i.imgur.com/1sH1wEu.jpg" title="source: imgur.com" /></a>
</p>
<br />
<br />

Step 8. Open IIS as an Admin, register PHP, then restart the server 


<p align="center">
<a href="https://imgur.com/iKulluD"><img src="https://i.imgur.com/iKulluD.jpg" title="source: imgur.com" /></a>
</p>
<br />
<br />

8b.
<p align="center">
<a href="https://imgur.com/jsplW34"><img src="https://i.imgur.com/jsplW34.jpg" title="source: imgur.com" /></a>
</p>
<br />
<br />

8c.
<p align="center">
<a href="https://imgur.com/o5wanr5"><img src="https://i.imgur.com/o5wanr5.jpg" title="source: imgur.com" /></a>
</p>
<br />
<br />

8d.
<p align="center">
<a href="https://imgur.com/u6lNcbw"><img src="https://i.imgur.com/u6lNcbw.jpg" title="source: imgur.com" /></a>
</p>
<br />
<br />

Step 9. Install osTicket v1.15.8


<p align="center">
<a href="https://imgur.com/dzHD98t"><img src="https://i.imgur.com/dzHD98t.jpg" title="source: imgur.com" /></a>
</p>
<br />
<br />

9b. Copy “upload” folder to c:\inetpub\wwwroot
<p align="center">
<a href="https://imgur.com/vFOJ8NQ"><img src="https://i.imgur.com/vFOJ8NQ.jpg" title="source: imgur.com" /></a>
</p>
<br />
<br />

9c. Within C:\inetpub\wwwroot, rename “upload” to “osTicket”
<p align="center">
<a href="https://imgur.com/qf5rktp"><img src="https://i.imgur.com/qf5rktp.png" title="source: imgur.com" /></a>
</p>
<br />
<br />

Step 10. Note that some extensions are not enabled
 
Go back to IIS, sites -> Default -> osTicket and double click PHP manager

<p align="center">
<a href="https://imgur.com/TwzlzA2"><img src="https://i.imgur.com/TwzlzA2.jpg" title="source: imgur.com" /></a>
</p>
<br />
<br />

10b. Click “Enable or disable an extension” and enable these extensions: php_imap.dll, php_intl.dll, php_opcache.dll

<p align="center">
<a href="https://imgur.com/1xujTV8"><img src="https://i.imgur.com/1xujTV8.jpg" title="source: imgur.com" /></a>
</p>
<br />
<br />

10c. Install the three .dll extensions as shown below

<p align="center">
<a href="https://imgur.com/Mhv6MWu"><img src="https://i.imgur.com/Mhv6MWu.jpg" title="source: imgur.com" /></a>
</p>
<br />
<br />

Step 11. After navigating to http://localhost/osTicket/setup/install, rename the ost-config.php file (see below) and click continue.

- From: C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php
- To: C:\inetpub\wwwroot\osTicket\include\ost-config.php

<p align="center">
<a href="https://imgur.com/1FcPJCw"><img src="https://i.imgur.com/1FcPJCw.jpg" title="source: imgur.com" /></a>
</p>
<br />
<br />

Step 12. After changing the ost-config.php file and clicking continue and you should see the following  screen:

<p align="center">
<a href="https://imgur.com/4gJUJ1E"><img src="https://i.imgur.com/4gJUJ1E.jpg" title="source: imgur.com" /></a>
</p>

Once the above information is filled in click save changes at the bottom of the screen.
<br />
<br />

12b. After saving you should see this screen. Click continue at the bottom of the screen.

<p align="center">
<a href="https://imgur.com/hhEHVdv"><img src="https://i.imgur.com/hhEHVdv.jpg" title="source: imgur.com" /></a>
</p>
<br />
<br />

Step 13. Back in osTicket Click the Dashboard tab and you should see the following screen:

<p align="center">
<a href="https://imgur.com/dH3L0vF"><img src="https://i.imgur.com/dH3L0vF.jpg" title="source: imgur.com" /></a>
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
<a href="https://imgur.com/ZhRDtni"><img src="https://i.imgur.com/ZhRDtni.png" title="source: imgur.com" /></a>
</p>
<br />
<br />

14b. After you click open you should see the following screen:

<p align="center">
<a href="https://imgur.com/zR6CqqT"><img src="https://i.imgur.com/zR6CqqT.png" title="source: imgur.com" /></a>
</p>
<br />
<br />

Success! You have installed osTicket!
Thank You for reading!

For the the osTicket configuration tutorial in this series go <a href=https://github.com/tarronacuff/osTicket-Configuration>here</a></h2>
