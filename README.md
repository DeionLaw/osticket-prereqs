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

![Screenshot 2025-02-03 102725](https://github.com/user-attachments/assets/27da3bbb-91fa-4035-bf23-f48f1a140949)
<p>
Once again in the files/folder provided, install PHP Manager for IIS (PHPManagerForIIS_V1.5.0.msi) and the Rewrite Module (rewrite_amd64_en-US.msi). The files are highlited above, simply follow the prompts that are given.
</p>
<br />

![Screenshot 2025-02-03 105006](https://github.com/user-attachments/assets/9e978742-2aee-48fc-98a7-a972d0bb8039)
![image](https://github.com/user-attachments/assets/d98730a1-a8c4-4a2f-85d1-769c6bec2572)
<p>
  Next we will create a folder on the root of the C drive and extract the files from the php-7.3.8-nts-Win32-VC15-x86 zip file to this location. This is shown in the first multiwindow screenshot above. After you should be left with what is shown in the second screenshot.
</p>

