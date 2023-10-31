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
- Windows 10 server

<h2>List of Prerequisites</h2>

- Set up an Azure Virtual Machine (VM) environment (Windows 10 4 vCPUs Recommended) 
- Install the files from this link on your Azure virtual machine http://tiny.cc/bl7dvz
- Install Web Platform Installer
- Install C++ Redistributable
- Install MySQL and set up username and password
      - For the username (root) and for the password (Password1234) This username and password is what I used during the lab.
- Configure permissions and install osTicket


  

<h2>Installation Steps</h2>

<p>


    
 <li>In your VM, go to the <b>Control Panel</b> and head to <b>Programs</b>. </li>
    <li>Check under <b>Program and Features</b> click on <b>Turn Windows features on or off</b></li>
    <li>Head over to the list and check the box for <b>Internet Information Services</b></li>
    <li>Expand the list for <b>Internet Information Services</b>, navigate to <b>World Wide Web Services</b> then expand that to find <b>Application Development Features</b>, expand that and check the box for <b>CGI</b>.</li>
    <li>Before closing, make sure the boxes under <b>Common HTTP Features</b> in World Wide Web Services are checked.</li>
  
![image](https://github.com/JosiahAllen03/osticket-prereqs/assets/147882549/3680976d-af20-4951-b39e-d0a6dda6dd9d)

</p>
<p>

</p>
<br />

![image](https://github.com/JosiahAllen03/osticket-prereqs/assets/147882549/e63670a1-d000-4ff3-bf92-4f50e5c77f8c)

<p>
  
<li> To double-check if everything is set correctly head to your VM browser and search 127.0.0.1. This should take you to the Internet Information Services webpage.</li>
  
</p>
<p>

</p>
<br />

<p>
  
![image](https://github.com/JosiahAllen03/osticket-prereqs/assets/147882549/7dc12426-dda5-4766-a2fe-55f58bef11d1)

</p>
<p>
</p>
<br />

![image](https://github.com/JosiahAllen03/osticket-prereqs/assets/147882549/9dff7247-4f16-4064-a23c-aea1e96ee5f9)
  
![image](https://github.com/JosiahAllen03/osticket-prereqs/assets/147882549/f9965e08-fd92-40d5-9456-661e2cde0770)

- We are going to create a PHP folder in our C: Directory
    
![image](https://github.com/JosiahAllen03/osticket-prereqs/assets/147882549/fe346893-eb84-4397-90f8-ebf4c2ed3279)

![image](https://github.com/JosiahAllen03/osticket-prereqs/assets/147882549/38117a00-b3cf-4da3-8656-acdc7c9b0c2a)

- From here we then want to head to our downloads and extract our PHP file that we downloaded earlier to our C: directory and the file will be the PHP file we created recently.
  
![image](https://github.com/JosiahAllen03/osticket-prereqs/assets/147882549/723537a0-48bc-412d-b6a2-3e9cf339555b)

- Go ahead and also go back to downloads and install Microsoft Visual C++ which was one of the files we downloaded at the start. Open and install like normal.
  
![image](https://github.com/JosiahAllen03/osticket-prereqs/assets/147882549/5e7e92b2-38d9-403f-ab3a-368ccfc6c409)

- After that finishes downloading we can also start to download the MYSQL server. We want to make sure we have the "Launch Instance Configuration Wizard" box checked. We also will have a standard Configuration selected as well. 
  
![image](https://github.com/JosiahAllen03/osticket-prereqs/assets/147882549/ad9e2c54-a2a1-4223-a18d-3a18a155d744)

- make sure to remember your sign-in. While it's not best to write passwords down since this is a lab I used the notepad.
    - For our Username I set it as "root" and for our password, I set it as "Password1234" which are both easy to remember, feel free to put whatever works best for you.
      
![image](https://github.com/JosiahAllen03/osticket-prereqs/assets/147882549/069f1143-040b-467a-b2e2-c356951ac92b)

- Once that is finished we will then search IIS and select run as admin
  
![image](https://github.com/JosiahAllen03/osticket-prereqs/assets/147882549/0872e2fa-366f-4435-b896-191394c018ef)

- Click on php rewrite
  
![image](https://github.com/JosiahAllen03/osticket-prereqs/assets/147882549/71e08883-fe31-401c-9f38-8569da98b539)

- Once open press register new php then select the three dots
  
![image](https://github.com/JosiahAllen03/osticket-prereqs/assets/147882549/c123e4aa-891d-4d5a-9424-39f3f625a1c7)

- From there we will head to this PC, then our C drive, and next our php folder. Once in the folder, we will select php-cgi. We have now selected a new path for our application.
  
![Screenshot_2023-10-22_094131](https://github.com/JosiahAllen03/osticket-prereqs/assets/147882549/27d67334-71c9-4856-a0eb-a153d90b0ff9)

- After what I like to do is restart the web server. Head back to our Web server then on the far right press restart. We do this to make sure our new path is in place.
  
![image](https://github.com/JosiahAllen03/osticket-prereqs/assets/147882549/a408ea8c-4375-4000-960a-f2798e49e9ab)

- For this part, we want to open two tabs of our file explorer. In one head to our OS Ticket download. In the other go to this pc, C drive, inetpub, then wwwroot. We are going to take our uploads file from OS ticket and drop it into wwwroot folder
  
![image](https://github.com/JosiahAllen03/osticket-prereqs/assets/147882549/9e1aab41-5bb6-4d5d-a8ac-5abdd51f87c2)

- We then want to rename our Uploads folder to "osTicket"
  
![image](https://github.com/JosiahAllen03/osticket-prereqs/assets/147882549/bfbb0fa0-5931-4be2-a469-a3d10decfceb)

- We can then open IIS as and admin again, then select on the left sites, Default web site, then select the osTicket folder. In this folder on the far right we want to click on the Browse *80 folder
  
![image](https://github.com/JosiahAllen03/osticket-prereqs/assets/147882549/2e5464ec-b232-4c70-91e7-501e4e51cb5e)

- We now should be taken to the osTicket Install webpage.
  - You should notice we have a few red Xs. We will be turning it into green check marks. So we can head back over to ISS to fix those.
    
![image](https://github.com/JosiahAllen03/osticket-prereqs/assets/147882549/0b5c1dc8-295a-48b4-adaa-01d0645a84b8)

- Once back in ISS we can head back to our osTicket folder, head to php manager then select at the bottom Enable or disable an extension
  
![image](https://github.com/JosiahAllen03/osticket-prereqs/assets/147882549/a5681af2-2146-4403-b30a-dbfca37388e0)

- Go ahead and enable these settings. After if you refresh the osTicket Web page those Xs should turn to green check marks!
    - Enable: php_imap.dll
    - Enable: php_intl.dll
    - Enable: php_opcache.dl
      
![image](https://github.com/JosiahAllen03/osticket-prereqs/assets/147882549/f3f4602a-b265-44b1-8a21-9fc4f0fb7d34)

- We also want to change a file name in our wwwroot folder. Head to this pc, C drive, Inetpub, wwwroot, osTicket, include, Then scroll down till you see a file called ost-sampleconfig.php. We want to change this to say "ost-config.php"
  
![image](https://github.com/JosiahAllen03/osticket-prereqs/assets/147882549/a3ceaf0a-7de1-41d9-baa1-0cc12e85cf92)

- Once finished we want to make sure the permissions on this file are set to everyone. So right-click the file, head to properties, then to security. Once on this page, we can head to advanced and then disable inheritance
  
![image](https://github.com/JosiahAllen03/osticket-prereqs/assets/147882549/b79fcfa7-9309-4f76-9548-aa6e40f48355)

- A new pop-up should appear, we then want to press Remove all Inherited Permissions
  
![image](https://github.com/JosiahAllen03/osticket-prereqs/assets/147882549/96bb8782-6373-4671-80ac-232c1c805bf0)

- After disabling we can press add, then we want to press select a principle. Here we can type "everyone" check names then press okay. This has given everyone on this computer full access to this file.
    - Also press full control on the basic permissions page when prompted. Now head back to osTicket webpage and press continue.

![image](https://github.com/JosiahAllen03/osticket-prereqs/assets/147882549/f5bf2612-ef73-4f75-a45f-a4d313b5abd5)

- Feel free to fill out the information. Make sure you remember it as we will need it later on. I wrote mine down on a notepad. The email doesn't matter much just put something simple and easy to remember.
  
![image](https://github.com/JosiahAllen03/osticket-prereqs/assets/147882549/ee0ba691-c2e2-4bf2-94c7-931f346a07df)

- To set up our database on osTicket we will head back to our downloads page and download HeidiSQL, and install it like normal.

![image](https://github.com/JosiahAllen03/osticket-prereqs/assets/147882549/0d5a3a78-51d1-42e8-87a5-9db2a07d8af8)

- Once Heidi opens we will press new at the bottom left, then enter whatever password you used for your osTicket setup or a password you will remember. After entering username and password click open at the bottom.
  
![image](https://github.com/JosiahAllen03/osticket-prereqs/assets/147882549/a91d2e00-b955-4ea9-8439-13610b220de3)

![image](https://github.com/JosiahAllen03/osticket-prereqs/assets/147882549/a9d76de8-17c2-4296-942c-b78f40acd716)

- Within Heidi what we need to do is create a new database. So we can right-click under the test data base and select new then database. We can name this new database osTicket

![image](https://github.com/JosiahAllen03/osticket-prereqs/assets/147882549/32eff2a3-fa1b-4562-9408-37596e3c21ff)

- Now heading back to our osTicket webpage we will enter our SQL username and password which we saved from before. For the MySQL Database section, we will put the database we just created called osTicket. 
  
![image](https://github.com/JosiahAllen03/osticket-prereqs/assets/147882549/a59e05dc-86a2-467d-9ab4-4b493a3b5430)

- Then press install, if everything is correct you should see this page that says Congratulations.
  
![image](https://github.com/JosiahAllen03/osticket-prereqs/assets/147882549/7930aa0b-91e9-4796-8230-712480d695dc)

- This link should take you to the admin sign-on page which you should now be able to sign into. http://localhost/osTicket/scp/login.php


