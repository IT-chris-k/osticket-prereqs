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

- Item 1
- Item 2
- Item 3
- Item 4
- Item 5

<h2>Installation Steps</h2>

<p>
 <img width="798" alt="image" src="https://github.com/IT-chris-k/osticket-prereqs/assets/150845863/5c97bcbb-11bd-4724-b124-5ea2714e03c4">

<p>
  Go to azure portal, and create a virtual machine that is running Windows 10 Pro, with at least 2 cores.
  When creating a Virtual Machine, create new Resource group and Virtual machine, and name it rg-osTicket and osTicket, respectively.
</p>




<br />



![image](https://github.com/IT-chris-k/osticket-prereqs/assets/150845863/e8b8bb61-06f6-4d9d-b624-cc60a0712758)

Extract all files into the downloads folder


<br />



![image](https://github.com/IT-chris-k/osticket-prereqs/assets/150845863/083d7649-a570-42c0-aa04-1870554b1233)



<p>
Under folders World Wide Web Services -> Application Development Features ->
 check off CGI , Common HTTP Features
AND IIS Management Console
Internet Information Services -> Web Management Tools -> IIS Management Console
 check off, IIS Management Console
then click OK.
To check if everything is done correctly, search the loopback address on the web browser. (127.0.0.1).

IIS is an internet based web server used to exchange web content with internet users. In this case , it will be used to host the osTicket ticketing program.


</p>

<br />


![image](https://github.com/IT-chris-k/osticket-prereqs/assets/150845863/f15104b2-9195-4776-a90b-b323c8a3d78c)

![image](https://github.com/IT-chris-k/osticket-prereqs/assets/150845863/6de94f33-dbee-4717-8738-6bdcf00900a7)

<p> Create a PHP folder and extract all the contents of php-7.3.8-nts into it. Open up IIS in the start menu and double-click on to the PHP manager(that we previously installed) and register new PHP version.
Browse into the PHP folder a search for a file called php-cgi.exe then restart the webserver on the right side of the screen.
(It is recommended to restart, whenever there is modification to the webserver)


</p>



<br />


![image](https://github.com/IT-chris-k/osticket-prereqs/assets/150845863/b88fef8b-79c1-48cc-8b92-45fa5dc4603c)

In the Download folder where everything was extracted to, open the osTicket folder.
Copy “upload” folder to c:\inetpub\wwwroot, and rename “upload” to “osTicket”


<br />

![image](https://github.com/IT-chris-k/osticket-prereqs/assets/150845863/8cfded62-0952-4afa-a920-8db623742e0c)

<p>
 In IIS on the left hand side, open up the Sites -> Default Web Site -> osTicket,
 and on the right hand site click Browse*:80, this will automatically open a website that shows whether all the components of osTicket system is in place to be in working order.
 There will be a few "x's", we will get to that next.
 
</p>

![image](https://github.com/IT-chris-k/osticket-prereqs/assets/150845863/07d47663-5c50-4279-b172-8fc96e666dcb)

In IIS, go to PHP manager -> PHP Extensions
enable :
- php_imap.dll
- php_intl.dll
- php_opcache.dll

<br />

![image](https://github.com/IT-chris-k/osticket-prereqs/assets/150845863/80f992ab-a427-47f7-a567-b7c16c31f1f7)

The website should look like this after the extensions have been enabled


<br />





![image](https://github.com/IT-chris-k/osticket-prereqs/assets/150845863/b264288a-e4ee-457d-8b8e-125cb2b89ff4)


Go into the folder C://inetpub/wwwroot/osTicket/include/
rename the file ost-sampleconfig.php into ost-config.php

![image](https://github.com/IT-chris-k/osticket-prereqs/assets/150845863/43bdf511-f1ae-42d8-a190-f1bfdd5411ec)
 
Right-click ost-config.php -> Properties -> Security -> Advanced -> Disable Inheritance -> Remove All Inherited Permissions -> Add Permissions -> Principal-> Type "everyone" in the space provided -> Check names -> OK -> Full control -> OK -> Apply -> OK -> OK

This allows everyone to have permissions to osTicket.

<br />



<br />

From the download folder install the following in this order:
-  VC_redist.x86.exe.
-  MySQL 5.5.62 (mysql-5.5.62-win32.msi)
-  Heidi SQL

MySQL is a sql server to store information within the osTicket and HeidiSQL allows us to connect to the MySQL server and setup a database that osTicket is able to use.
When installing MySql install a typical setup under standard configuration. Remember to save the root password somewhere safe. We will be needing it for when we complete the setuo for osTicket.

<br />

![image](https://github.com/IT-chris-k/osticket-prereqs/assets/150845863/8b02aa5c-c528-4a31-8c7a-b3ee9ad2a3fd)


Go back to the osTicket Installer on the Browser, press continue and fill in all the blank spaces
Use the mySQL information under database settings.


Browse to your help desk login page : 
- http://localhost/osTicket/scp/login.php
  

For end users the osTicket URL is:
- http://localhost/osTicket/

Congratulation, hopefully osTicket is installed with no errors!


