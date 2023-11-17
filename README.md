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


![image](https://github.com/IT-chris-k/osticket-prereqs/assets/150845863/b88fef8b-79c1-48cc-8b92-45fa5dc4603c)

In the Download folder where everything was extracted to, open the osTicket folder.
Copy “upload” folder to c:\inetpub\wwwroot, and rename “upload” to “osTicket”


<br />

![image](https://github.com/IT-chris-k/osticket-prereqs/assets/150845863/f15104b2-9195-4776-a90b-b323c8a3d78c)
<p> Create a PHP folder and extract all the contents ofphp </p>

<br />

<br />





