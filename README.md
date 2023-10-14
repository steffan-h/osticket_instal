<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>

<h1>osTicket - Prerequisites and Installation</h1>
This section outlines the prerequisites and installation of the open-source help desk ticketing system osTicket.<br />


<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Internet Information Services (IIS)

<h2>Operating Systems Used </h2>

- Windows 10</b> (22H2)

<h2>List of Prerequisites</h2>

- PHP Manager for IIS
- Rewrite Module
- PHP
- Visual C++
- MySQL
- HeidiSQL
- osTicket

<h2>Installation Steps</h2>
<p>
  After setting up and logging into the virtual machine, go to Windows Features and install/enable <b>IIS with CGI</b>, <b>Common HTTP Features</b>, and <b>IIS Management Console</b>.
</p>

![image](https://github.com/steffan-h/osticket_instal/assets/146549173/6285cdc6-d019-477d-9410-6e6092c5eaee)
<br />

<p>
  Download and install <b>PHP Manager for IIS</b> and the <b>Rewrite Module</b>.
</p>
<p>
  Download <b>PHP</b>, create the directory <i>C:\PHP</i>, and unzip the contents of PHP into <i>C:\PHP</i>.
</p>
<p>
  Download and install <b>Visuall C++</b> and <b>MySQL</b>. When installing MySQL, choose Typical Setup and Launch Configuration Wizard after install. From there, choose Standard Configuration and enter a password of your choice.
</p>
<p>
  Open IIS as an Admin. Go to <i>Sites -> Default -> osTicket</i> and register PHP from within IIS then reload IIS.
  
![image](https://github.com/steffan-h/osticket_instal/assets/146549173/e81c3da5-cb49-4808-8b32-3dc68da7e45b)
  
![image](https://github.com/steffan-h/osticket_instal/assets/146549173/e04492c1-9338-4cb3-9a83-1912b97c939e)
</p>
<p>
  Download and install <b>osTicket</b>. Extract and copy "upload" folder to <i>C:\inetpub\wwwroot</i>. Rename "upload" to "osTicket". Reload IIS.

![image](https://github.com/steffan-h/osticket_instal/assets/146549173/64272864-b46e-44c5-923e-97b993253d5a)
</p>
<p>
  In IIS, go to <i>Sites -> Default -> osTicket</i>. Double-click "PHP Manager" then click "Enable or disable an extension”. From there, enable <b>php_imap.dll</b>, <b>php_intl.dll</b>, and <b>php_opcache.dll</b>.
</p>

![image](https://github.com/steffan-h/osticket_instal/assets/146549173/f9ae5b89-49a2-49dd-a128-ff3b308306dd)

![image](https://github.com/steffan-h/osticket_instal/assets/146549173/1b1d4067-2b46-4238-a66e-c92fd0f7a863)
<p>
<p>
  Go to <i>C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php</i> and rename it to <i>C:\inetpub\wwwroot\osTicket\include\ost-config.php</i>

![image](https://github.com/steffan-h/osticket_instal/assets/146549173/8ccde0c9-7c36-4f7e-ae1b-ebb8ba195562)
</p>
<p>
  Right-click "ost-config.php" and go to <i>Properties -> Security -> Advanced -> Disable inheritance -> Remove All</i>. Then give new permissions to Everyone.

![image](https://github.com/steffan-h/osticket_instal/assets/146549173/5a61d7dc-cb3d-4aab-b09b-7f7afa2f148e)

![image](https://github.com/steffan-h/osticket_instal/assets/146549173/3e88f3ad-002e-4c2e-af5c-965ab10e70d7)
</p>
<p>
  Download and install <b>HeidiSQL</b>. Open it, create a new session with username root and a password of your choice. Connect to the session and create a database called "osTicket"

![image](https://github.com/steffan-h/osticket_instal/assets/146549173/32dff493-0dff-438f-a2ea-ae3cc6365200)

![image](https://github.com/steffan-h/osticket_instal/assets/146549173/8c4b92c5-3027-4b65-b8e6-bf1b9f7bdf46)
</p>
<p>
  Going back to the osTicket folder in IIS (<i>Sites -> Default -> osTicket</i>), on the right side of the window click “Browse *:80” and setup osTicket. Under the Database Settings, be sure to have the MySQL Database as osTicket, the MySQL Username as root and the MySQL Password as the one you chose previously. When all fields are filled out, click "Install Now"

  ![image](https://github.com/steffan-h/osticket_instal/assets/146549173/0f8e0756-474d-4da0-a3d9-2be7465ddf9b)
</p>
<p>
  After all this, you can delete <i>C:\inetpub\wwwroot\osTicket\setup</i> and set the permissions on <i>C:\inetpub\wwwroot\osTicket\include\ost-config.php</i> as "Read" only.
</p>
<p>
  Congrats. You should now have a working osTicket ticketing system. To access the help desk login page, use <i>http://localhost/osTicket/scp/login.php</i> and to access the end user page use <i>http://localhost/osTicket/</i>
</p>
<br />
