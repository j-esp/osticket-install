![image](https://github.com/user-attachments/assets/4df7de56-a264-4679-9df5-64f285e9c6f8)

<h1>osTicket - Installation</h1>
In this activity, I will install osTicket from scratch, including all necessary installation files. Several preliminary steps are required before deploying the ticketing system. The referenced files can be found <a href="https://drive.google.com/drive/u/2/folders/1APMfNyfNzcxZC6EzdaNfdZsUwxWYChf6"> here</a>.

<h2>Technologies and Platforms</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop Connection
- Internet Information Services (IIS)
- MySQL

<h2>Operating Systems Used </h2>

- Windows 10 Pro</b> (22H2)


<h2>Installation</h2>

![image](https://github.com/user-attachments/assets/150fc80e-4751-447e-9fb5-2e08545c6fe7)

<p>
Before installation, Internet Information Services (IIS) must be enabled, as it is essential for osTicket to function. To enable IIS, go to the Control Panel, select "Programs," and then click "Turn Windows Features On or Off." In this menu, expand "Internet Information Services," select "Web Management Tools," and enable "IIS Management Console." Next, expand "World Wide Web Services," select "Application Development Features," and enable "CGI." Proceed with these settings to complete the IIS configuration.
</p>

![image](https://github.com/user-attachments/assets/8607c319-45ef-46e0-a8b6-3e03d4f8f6b7)

<p>
After enabling IIS, download and install PHP Manager for IIS (PHPManagerforIIS_V1.5.0.msi) from the installation files index. Next, install the Rewrite Module (rewrite_amd64_en-US.msi). 
</p>

![image](https://github.com/user-attachments/assets/e6b65f83-7f85-42f1-82f0-572adf65ba5a)

<p>
After installing the Rewrite Module, create a new folder at C:\PHP on the C: drive. Then, extract the contents of the PHP 7.3.8 zip file (php-7.3.8-nts-Win32-VC15-x86.zip) into this folder. 
</p>

![image](https://github.com/user-attachments/assets/2cecfa36-ed65-4c7e-848b-4d3866b49bba)

<p>
Next, download and install VC_redist.x86.exe from the installation files.
</p>

![image](https://github.com/user-attachments/assets/6d3d84a1-1777-4cc0-90b0-405d91c27939)

<p>
Next, download and install MySQL 5.5.62 (mysql-5.5.62-win32.msi) using the Typical Install option. In the Configuration Wizard, choose Standard Configuration, install MySQL as a Windows Service, and ensure that "MySQL Server Launch" is checked. For this activity, use "root" as the username and "Password1" as the password.
</p>

![image](https://github.com/user-attachments/assets/1e74b89e-e2a6-4b7d-ace4-30f17e52a099)
![image](https://github.com/user-attachments/assets/f239d011-ac3b-4478-a9e0-a49b24411f82)

<p>
IIS must be configured before installing osTicket. Open IIS as an administrator, select PHP Manager, and register the new PHP version by browsing to the PHP CGI executable file (php-cgi.exe) in the previously created PHP folder. After registering the PHP version, reload the IIS server through the management console.
</p>

![image](https://github.com/user-attachments/assets/bfab71bc-f734-49af-8ba2-733b0908a547)

<p>
Download osTicket v1.15.8 from the installation files, then extract and copy the "upload" folder to c:\inetpub\wwwroot. Rename the folder from "upload" to "osTicket" and reload the IIS server. 
</p>

![image](https://github.com/user-attachments/assets/2f125ef3-3a48-446b-ad78-4efec4cda7bc)
![image](https://github.com/user-attachments/assets/2a5c2ab3-5bf4-4dae-949d-cb32bb897cf4)
![image](https://github.com/user-attachments/assets/ae37e608-1e08-484c-990f-0b4d238c02b8)

<p>
In the IIS console, navigate to Sites -> Default -> osTicket. Click on *"Browse :80" to access the osTicket installation page. Prior to installation, ensure that certain extensions are enabled. To enable them, go to PHP Manager within the osTicket menu in IIS and select "Enable or disable an extension." Enable the following extensions: php_imap.dll, php_intl.dll, and php_opcache.dll. 
</p>

![image](https://github.com/user-attachments/assets/4b7d1630-aeb2-4189-93f7-9021e97716cc)
![image](https://github.com/user-attachments/assets/1bc663a0-9242-44a9-a30a-2b047854e30c)
![image](https://github.com/user-attachments/assets/662ba6d0-ddd4-4c7c-bb0c-58d15352261c)

<p>
Next, navigate to C:\inetpub\wwwroot\osTicket\include and rename ost-sampleconfig.php to ost-config.php. Adjust the file permissions by right-clicking the file, selecting Properties, and modifying the permissions as follows: disable inheritance, remove all existing permissions, and then grant Everyone Full Control. 
</p>

![image](https://github.com/user-attachments/assets/ca312924-f911-4de7-9fa9-3436acecdf83)
![image](https://github.com/user-attachments/assets/9820d014-f222-4e8d-9bb8-2a9a13231ea8)
![image](https://github.com/user-attachments/assets/5c2ae6f8-38ce-4bc5-964c-dc9066dd8e6a)

<p>
Lastly, install HeidiSQL using the provided installation files. Open HeidiSQL, create a new session, and enter the MySQL password used during installation. In the new session, right-click Unnamed, select Create new database, and name the database osTicket. 
</p>

![image](https://github.com/user-attachments/assets/e3cb6031-f8df-4c81-a30f-1001512daf21)
![image](https://github.com/user-attachments/assets/b972eb35-d88b-4276-8740-a5d4d7716c7f)

<p>
The osTicket installation is now complete. Before using it, delete the setup folder located in C:\inetpub\wwwroot\osTicket. Additionally, revert the permissions for ost-config.php in C:\inetpub\wwwroot\osTicket\include so that Everyone has Read access only. 
</p>

<h2>osTicket Installed</h2>
With osTicket successfully installed and operational, I can now delve into the workings of ticketing systems. These systems are commonly used in IT support to address and resolve technical issues. 
