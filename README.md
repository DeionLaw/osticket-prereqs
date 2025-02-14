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

- Physical or VM running Windows (Windows 10 is used in this example)
- The files provided here: https://drive.usercontent.google.com/download?id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD&export=download&authuser=0

<h2>Installation Steps</h2>

![Screenshot 2025-02-03 100819](https://github.com/user-attachments/assets/680724ad-65de-490b-afaa-9a98b252d4be)
<p>
Download the files through the link provided above. Extract the folder to somewhere that makes sense for you, and you will be left with a folder containing the files shown in the picture above.
</p>
<br />

---

![Screenshot 2025-02-03 102725](https://github.com/user-attachments/assets/a44dbfa2-69b6-4be9-8a26-258c6d6971a8)
<p align="center">
ENABLING IIS (WITH CGI):
</p>
<p>
  Hit the windows key, type, and click "Turn Windows features on or off".
</p>
<p>
  A window will pop up with many options and dropdowns, the only one we will need to check mark will be CGI.
</p>
<p>
  This is found in 'Internet Information Services' > 'World Wide Web Services' > 'Application Development Features' > 'CGI'. 
</p>
<p>
  Checking this box should also check all the parent options as well. The location is shown and highlighted (poorly) in the picture above.
</p>
<p>
  Follow the prompts and IIS with CGI will be enabled.
</p>
<br />

---

![Screenshot 2025-02-03 104322](https://github.com/user-attachments/assets/681a8d24-bd01-4231-bd2c-332f89a29a83)

<p>
Once again in the files/folder provided, install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi) and the Rewrite Module (rewrite_amd64_en-US.msi). The files are highlited above, simply follow the prompts that are given.
</p>
<br />

---

![Screenshot 2025-02-03 105006](https://github.com/user-attachments/assets/9e978742-2aee-48fc-98a7-a972d0bb8039)
![image](https://github.com/user-attachments/assets/d98730a1-a8c4-4a2f-85d1-769c6bec2572)
<p>
  Next we will create a folder on the root of the C drive called 'PHP' and extract the files from the php-7.3.8-nts-Win32-VC15-x86 zip file to this location. This is shown in the first multiwindow screenshot above. After you should be left with what is shown in the second screenshot.
</p>

---

![Screenshot 2025-02-03 105714](https://github.com/user-attachments/assets/90fde048-26f2-4575-8510-de5332a29d0c)
<p>
  Next we will install (VC_redist.x86) and then (mysql-5.5.62-win32). The 2 files are shown in the screenshot above. When given the options on the mysql install, choose typical setup, launch the configuration wizard after and when prompted to set the security settings set your own root password, do NOT forget this password.
</p>

---

![Screenshot 2025-02-03 113847](https://github.com/user-attachments/assets/a239bf53-214b-4dab-b2ed-2b0248b0f848)
<p>
  Next we will open IIS as an admin, click on PHP Manager, and provide the PHP executeable (most likely) at C:\PHP\php-cgi.exe. The steps are shown and highlighted above.
</p>

<p>
  Afterwards, click stop and then start from the action bar on the right of IIS.
</p>

---

![Screenshot 2025-02-03 114630](https://github.com/user-attachments/assets/15700f77-0b2b-4e17-9e29-3734d0296db1)

<p>
  Next unzip the 'osTicket-v.1.15.8' zip file provided and copy/move the 'upload' folder to 'C:\inetpub\wwwroot', afterwards, change the name from 'upload' to 'osTicket'. Restart the server as we did earlier by clicking stop and start from the action bar in IIS.
</p>

---

![Screenshot 2025-02-03 115051](https://github.com/user-attachments/assets/12eff5fc-ac87-4b8a-a3c2-3dbbef2425d1)

<p>
  Now, in IIS, we can use the dropdown on the left to go to 'Sites' > 'Default Web Site' > 'osTicket' and click 'Browse *:80' from the action bar to the right on IIS. osTicket should open up, and you'll have something that looks like the screenshots above.
</p>

---

![Screenshot 2025-02-03 120512](https://github.com/user-attachments/assets/ed1cca72-4aab-4b46-914f-ffc1b8c9f9b6)

<p>
  Next, we will have to enable some extensions, return back to 'Sites' > 'Default Web Site' and click 'PHP Manager' then 'Enable or disable an extension' as shown above.
</p>

---

![Screenshot 2025-02-03 121009](https://github.com/user-attachments/assets/dd434d05-363b-41ad-9da0-5b87c6dc0447)

<p>
  The extensions you will want to choose will be as follows: 1. 'php_imap.dll' 2. 'php_intl.dll' 3. 'php_opcache.dll', simply right click them, and click enable. Mine in the screenshot above are already enabled, yours will be in the lighter, disabled section.
</p>

---

![Screenshot 2025-02-03 121338](https://github.com/user-attachments/assets/84858617-00a1-4dfa-98f1-e7df5093c6d2)
<p>
  Next, inside the location at 'C:\inetpub\wwwroot\osTicket\include\' change the name of the file 'ost-sampleconfig.php' to 'ost-config.php'. After this right click the file, select 'Properties', 'security' from the tabs above the new window, click 'Advanced' near the bottom them 'Disabled inheritance' when the pop up comes up click 'Remove all inherited permissions from this object.' then click 'Add', at the top click 'Select a principal', in the box you can type 'everyone and push 'Check Names' to the right, click ok and select 'Full control'. This is not how you would approach this in real life, if you're setting this up in a real world environment, you would give access to those who need it. You can now choose 'Apply' and 'Ok'. You can now choose 'continue' from the osTicket page to continue.
</p>

---

![Screenshot 2025-02-03 123830](https://github.com/user-attachments/assets/9811d839-e6aa-4e33-8d55-ef34165020b0)

<p>
  Next, install HeidiSQL (HeidiSQL_12.3.0.6589_Setup) from the files provided. Simply click on the file shown above, leaves things default, and proceed through the prompts. Have 'Launch HeidiSQL' checked at the end of the installation. 
</p>

---

![Screenshot 2025-02-03 124133](https://github.com/user-attachments/assets/d394f054-e43e-4735-8cd7-08ce059a7b9f)

<p>
  When HeidiSQL opens click the new button and provide the root username and password that you set when you installed mySQL.
</p>

---

![Screenshot (1)](https://github.com/user-attachments/assets/66588a07-ba8d-453e-af9a-d562325cae8b)
![Screenshot 2025-02-03 125345](https://github.com/user-attachments/assets/943ea493-eb3f-44d1-8aa6-58e8892eda3d)


<p>
  Afterwards, right click the 'Unnamed', click 'Create new' > 'Database'. Set the name to 'osTicket', this is case sensitive.
</p>

---

![Screenshot 2025-02-03 125606](https://github.com/user-attachments/assets/bd073851-9c9f-49c0-8e51-c926c6913d72)

<p>
  Now you can finish the setup, providing the information that you want, and at the end using the root password we set in the mySQL setup.
</p>

<p>
  osTicket is now installed :) 
</p>
<p>
  The login page should be here: http://localhost/osTicket/scp/login.php
</p>
<p>
  and the endusers can login at: http://localhost/osTicket/ 
</p>

