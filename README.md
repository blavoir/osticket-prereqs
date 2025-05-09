
<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This tutorial outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Video Demonstration</h2>

- ### [YouTube: How To Install osTicket with Prerequisites](https://youtu.be/JIzKqU4gqOI)

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

<b>Disclaimer:</b> I am providing an zip file for easy convenience. Please do note that software generally will need to be updated whenever bugs, security vulnerabilities or patches need to be applied so download links for the individual components are also provided. 

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
Create a directory for <b>PHP and extract the PHP zip file to that directory.</b> Afterwards, install <b>Visual C++</b>.
</p>
<br />

<p>
<img src="https://i.imgur.com/IPZn1r0.gif" height="80%" width="80%" alt="Installing MySQL and configuring it"/>
</p>
<p>
Open and install <b>MySQL Server</b>. Then, within the configuration wizard set a password for the root account. Click next until the wizard is done installing and closed.
</p>
<br />

<p>
<img src="https://i.imgur.com/dPSQ7X2.gif" height="80%" width="80%" alt="Configuring IIS"/>
</p>
<p>
Open <b>IIS Management Console in admin mode</b>. Locate the PHP manager and click on "Register new PHP version". Locate the same directory where you previously extracted the PHP files and click on the "php-cgi" executable. Reload IIS by going to the home page and under Manage Server on the right side, clicking restart or stop and then start. Ensure that it is working by going in a browser and typing in <b>localhost</b> (should show an default windows page).
</p>
<br />

<p>
<img src="https://i.imgur.com/fa6nAd6.gif" height="80%" width="80%" alt="Installing osTicket"/>
</p>
<p>
Back to the setup files, inside the osTicket setup zip file, extract <b>only</b> the upload folder to the directory "C:\inpetub\wwwroot". Afterwards, <b>rename the upload folder to "osTicket"</b> <i>case sensitive</i>. Then, restart IIS. 
</p>
<br />

<p>
<img src=https://i.imgur.com/dPSQ7X2.gif" height="80%" width="80%" alt="Installing osTicket"/>
</p>
<p>
Within the IIS console, on the left side, go to <b>sites -> Default web site -> osTicket -> on the right side, nagivate to the website under Manage Folder</b>. Verify it works. Back to the IIS console, nagivate to the PHP Manager, scroll down to extensions and click on "Enable or disable an extension". <b>Enable both "php_intl.dll" and "php_opcache.dll"</b>. Refresh the website. 
</p>
<p><i>Note: If you get an error regarding PHP, it is likely that you didn't install Visual C++ which is found on the download page on the left side under the headline VS16&VS17. It is required in order for this to work.</i></p>
<br />


<p>
<img src="https://i.imgur.com/XmrAW8E.gif" height="80%" width="80%" alt="Editing config file"/>
</p>
<p>
Nagivate to the osTicket directory. Then, nagivate to /include and find the osTicket-sampleconfig.php. Rename it to ost-config.php. Right click go to properties -> Security -> Advanced -> Disable inheritance and remove all permissions. Assign new permissions and allow everyone full access temporarily.
</p>
<br />

<p>
<img src="https://i.imgur.com/aMeQlGR.gif" height="80%" width="80%" alt="Installing HeidiSQL"/>
</p>
<p>
Click Continue on the website and fill all of the information in the blank fields except the category Database settings. Finally, install HeidiSQL and then launch it. Click new on the bottom left, log into the session with the same account credentials you used when you installed MySQL. Create a new databse and name it "osTicket" case sensitive and save. Now, fill in the database settings with the name osTicket, and your account credentials. Then, click install now!
</p>
<br />

<h2>Congrats! You installed osTicket!</h2>
<p>
<img src="hhttps://i.imgur.com/0AWD9cC.png" height="80%" width="80%" alt="Finished installing osTicket"/>
</p>
<p>
This page should show pop up after the installation is completed. At the bottom, there should be useful links including the end user support page and the staff control panel. Those links are how your customers and your staff will be using to log in and interact with osTicket. osTicket is almost ready for configure however, there is one more last step.
</p>
<br />

<p>
<img src="https://i.imgur.com/zlOvEoA.gif" height="80%" width="80%" alt="Cleanup"/>
</p>
<p>
Before configuring, you need to nagivate back to the osTicket directory and delete the setup folder. Then, nagivate back to the include folder and set the permissions within the ost-config.php file to read only. After that, you are ready to start configuring osTicket.
</p>
<br />
