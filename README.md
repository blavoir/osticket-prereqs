![8](https://github.com/user-attachments/assets/6ec7b5ed-9826-4cee-884d-1e391cb31b46)# osticket-prereqs

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

- Windows 10</b> (22H2)

<h2>List of Prerequisites</h2>

<h3>Full Package</h3>

- [Download Complete Package](https://drive.google.com/file/d/1x-o6fiYYPW-pw7Nm2LWCijQ1Odys7FR9/view?usp=drive_link)</b>
(includes all files bundled together for the demonstration)

<h3>Download Individual Components</h3>

- [osTicket](https://github.com/osTicket/osTicket/releases/tag/v1.18.2)
- [PHP (includes Visual C++ installer on the site)](https://www.php.net/downloads.php)
- [PHP Manager for IIS](https://www.phpmanager.xyz/)
- [Rewrite Module for IIS](https://www.iis.net/downloads/microsoft/url-rewrite)
- [MySQL](https://dev.mysql.com/downloads/installer/)
- [HeidiSQL](https://www.heidisql.com/download.php)

Disclaimer: I am providing an zip file for easy convenience. Please do note that software generally will need to be updated whenever bugs, security vulnerabilities or patches need to be applied so download links for the individual components are also provided. 

<h2>Installation Steps</h2>

<p>
<img src="https://i.imgur.com/HQvRZbq.gif" height="80%" width="80%" alt="Enabling IIS from the Control Panel"/>
</p>
<p>
Go to the Control Panel and enable IIS by <b>Control Panel -> Uninstall a Program -> Turn Windows features on or off -> selecting Internet Information Services -> World Wide Web Servies -> Application Development Features -> CGI</b>. 
Ensure in the start menu you are able to find IIS management console by searching it up or enabling through <b>...->Web Management->IIS Management Console. </b>
</p>
<p>Afterwards within the setup files, install <b>PHP Manager for IIS</b> and the <b>Rewrite Module for IIS</b>.</p>
<br />

<p>
<img src="https://i.imgur.com/jtox6M0.gif" height="80%" width="80%" alt="Creating a directory for PHP and extracting setup files to it"/>
</p>
<p>
Create a directory for PHP and extract the PHP zip file to that directory. Afterwards, install Visual C++.
</p>
<br />

<p>
<img src="https://i.imgur.com/IPZn1r0.gif" height="80%" width="80%" alt="Installing MySQL and configuring it"/>
</p>
<p>
Open and install MySQL Server. Then, within the configuration wizard set a password for the root account. Click next until the wizard is done installing and closed.
</p>
<br />

<p>
<img src="https://i.imgur.com/nfwUtfj.gif" height="80%" width="80%" alt="Configuring IIS"/>
</p>
<p>
Open IIS Management Console in admin mode. Locate the PHP manager and click on "Register new PHP version". Locate the same directory where you previously extracted the PHP files and click on the "php-cgi" executable. Reload IIS by going to the home page and under Manage Server on the right side, clicking restart or start and then stop. Ensure that it is working by going in a browser and typing in localhost (should show an default windows page).
</p>
<br />

<p>
<img src="https://i.imgur.com/fa6nAd6.gif" height="80%" width="80%" alt="Installing OsTicket"/>
</p>
<p>
Back to the setup files, inside the OsTicket zipe file, extract only the upload folder to the directory "C:\inpetub\wwwroot". Afterwards, rename the upload to "osTicket" case sensitive. Then, restart IIS. 
</p>
<br />

<p>
<img src="https://i.imgur.com/9p1CLjW.gif" height="80%" width="80%" alt="Nagivating to osTicket installer and Enabling extensions"/>
</p>
<p>
Within the IIS console, on the left side, go to sites -> Default web site -> osTicket -> on the right side, nagivate to the website under Manage Folder. Verify it works. Back to the IIS console, nagivate to the PHP Manager, scroll down to extensions and click on "Enable or disable an extension". Enable both "php_intl.dll" and "php_opcache.dll". Refresh the website. 
</p>
<p>Note: If you get an error regarding PHP, it is likely that you didn't install Visual C++ which is found on the download page on the left side under the headline VS16&VS17. It is required in order for this to work.</p>
<br />

