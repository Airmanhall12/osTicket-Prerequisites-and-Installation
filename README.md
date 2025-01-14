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


<h2>Installation Steps</h2>

<p> 
  
# Step 1 - Setup Azure Virtual Machine

1. Log into Microsoft Azure - [https://portal.azure.com](https://portal.azure.com)                                               

![image](https://github.com/user-attachments/assets/0081727d-cebf-4b44-8c80-d074f8e7f707)

2. Search for "Virtual Machines" and click "Create/Azure Virtual Machine."

![image](https://github.com/user-attachments/assets/48109ad1-3440-41f4-b4a7-436ce636eb1c)

3. Create a "Resource Group" and name it "OS-Ticket."

![image](https://github.com/user-attachments/assets/b1984880-fa01-4e6c-90db-7e997be65dfd)

4. Go to "Virtual Machine Name" and name it "osticket-vm."

![image](https://github.com/user-attachments/assets/2db1afbe-e4c7-4acd-96e8-4974f546c1bb)

5. Under "Image," select "Windows 10 Pro, Version 22H2 - x64 Gen 2."

![image](https://github.com/user-attachments/assets/b17a3c8a-da3c-475c-a1d5-bf163a0d1494)

6. Under "Size," select "Standard_D2s_v3."

![image](https://github.com/user-attachments/assets/3e94050f-587c-4e02-8175-735f0a911910)

7. Under "Administrator Account," use the following credentials:
   - Username: `labuser`
   - Password: `Osticketlogin1!`

![image](https://github.com/user-attachments/assets/05217876-f3af-4370-ae65-f743ed2d77fa)

8. Under "Licensing," select "I confirm."

![image](https://github.com/user-attachments/assets/1c895885-39b2-401f-9f83-574259659989)

9. At the bottom, select "Review + Create."

![image](https://github.com/user-attachments/assets/cc607e29-e778-40ee-8120-8c9502f599f9)


---

# Step 2 - Log onto “osticket-vm” and Install “OS-Ticket Install Files”

1. In Azure, go to "Virtual Machines" and select "osticket-vm."

<img width="371" alt="image" src="https://github.com/user-attachments/assets/c70cacc6-6857-4ada-aefa-e7c0c502a945" />

2. Go to "Network Settings" and copy the "Public IP address."

![image](https://github.com/user-attachments/assets/5f485afd-79f8-4d8b-b8ef-536028a43b86)

3. Press the "Windows Key" and search for "Remote Desktop Connection."

![image](https://github.com/user-attachments/assets/cf595c51-936e-4ee9-ac4f-4f8113896ba9)

4. Input your "Public IP address" and "Username" for "osticket-vm."

![image](https://github.com/user-attachments/assets/a787f973-90f7-41b8-a81e-ebfb42b87877)

5. Select "Connect."

![image](https://github.com/user-attachments/assets/05eda516-8a1c-4c8c-922f-21951f4f2416)

6. Input your "Password" for "osticket-vm" and select "OK."

![image](https://github.com/user-attachments/assets/6e58e62f-d0e9-4569-871c-1b7bf6600195)

7. In "osticket-vm," open a web browser and go to [osTicket-Installation-Files](https://drive.google.com/uc?export=download&id=1b3RBkXTLNGXbibeMuAynkfzdBC1NnqaD).

8. Download `osTicket-Installation-Files.zip` and unzip it onto your Desktop.

![image](https://github.com/user-attachments/assets/60248dcd-aa93-4ee1-be74-3bc3882a2951)


---

# Step 3 - Enable IIS in Windows with CGI on "osticket-vm"

1. Press the "Windows Key" and search for "Control Panel."

![image](https://github.com/user-attachments/assets/05c06e9d-247a-4f8c-be29-302a299d14cf)

2. In "Control Panel," select "Programs."

![image](https://github.com/user-attachments/assets/c353d66f-0671-498b-b3b7-7f37197b7d2c)

3. Under "Programs and Features," select "Turn Windows Features On or Off."

![image](https://github.com/user-attachments/assets/598c1827-f8bc-4980-a7a3-2e2b74933f9e)

4. In "Windows Features," select "Internet Information Services."

![image](https://github.com/user-attachments/assets/5826ec9a-4c11-4cc3-8a0e-74add2842ffb)

5. Expand "Internet Information Services" > "World Wide Web Services" > "Application Development Features."

![image](https://github.com/user-attachments/assets/e2fe6233-9ccd-4552-a1c9-cb80f1552fe3)

6. Under "Application Development Features," select "CGI."

![image](https://github.com/user-attachments/assets/4a9a2684-6fa4-447a-a57b-3b9c8589df4d)

7. At the bottom, press "OK."

![image](https://github.com/user-attachments/assets/a758dbb1-fba2-42eb-806c-d02010fe8301)


---

# Step 4 - Install Files from "osTicket-Installation-Files" Folder

1. Open the "osTicket-Installation-Files" folder on your Desktop in "osticket-vm."

![image](https://github.com/user-attachments/assets/a4c46597-94b4-455d-a936-89106a697878)

2. Install `PHPManagerForIIS_V1.5.0.msi`.

![image](https://github.com/user-attachments/assets/74bacfe5-9a9a-4b80-8123-275a569f919d)

3. Install `rewrite_amd64_en-US.msi`.

![image](https://github.com/user-attachments/assets/18f81947-0141-4aeb-8b6c-25fd92b47e58)

4. Press "Windows Key + E" and select "Windows (C:)."

![image](https://github.com/user-attachments/assets/c92fe00c-53f4-46e3-86e0-a5362fb8a430)

5. In "Windows (C:)," create a "New Folder" and name it "PHP."

![image](https://github.com/user-attachments/assets/7e68bf47-a5bd-4de7-8214-f4b1ad582699)

6. Open the "osTicket-Installation-Files" folder, unzip `php-7.3.8-nts-Win32-VC15-x86.zip` into the `C:\PHP` folder.

![image](https://github.com/user-attachments/assets/912e4e40-c37d-48a3-9414-243ca1701c30)

7. Open the "osTicket-Installation-Files" folder and install `VC_redist.x86.exe`.

![image](https://github.com/user-attachments/assets/598d98f2-4164-44c4-b25c-27671e4a2884)

8. Open the "osTicket-Installation-Files" folder and install "MySQL 5.5.62" using the following credentials:
   - Username: `root`
   - Password: `root`
![image](https://github.com/user-attachments/assets/8ba6ec06-6f2e-4430-b5ba-1413c97f75b9)


---

# Step 5 - Open “IIS” as Admin and Configure “PHP”

1. Press "Windows Key" and search for "IIS" and select "Run as Admin."

![image](https://github.com/user-attachments/assets/6ed0c4d5-9235-476a-9fc2-7750a6ad3ea9)

2. In "IIS," select "PHP Manager."

![image](https://github.com/user-attachments/assets/a3aeeec9-cc1d-4272-947e-33923ca5b4b9)

3. In "PHP Manager," select "Register New PHP."

![image](https://github.com/user-attachments/assets/64b99f65-5e7b-4555-be97-7b6c62b816a3)

4. Browse and select `C:\PHP\php-cgi.exe`.

![image](https://github.com/user-attachments/assets/36b335ce-9b41-4ee6-bc53-93608cf5ef0a)

5. Close and reopen "IIS" and "Stop/Start Server."

![image](https://github.com/user-attachments/assets/bf05c71c-b91f-4314-9f17-76dcb03e8de2)


---

# Step 6 - Install “osTicket v1.15.8”

1. Open the "osTicket-Installation-Files" folder and open the "osTicket v1.15.8" folder.

![image](https://github.com/user-attachments/assets/2dcaef27-77cf-4079-8501-60505c989a21)

2. Copy the "Upload" folder.

![image](https://github.com/user-attachments/assets/91af53d9-33fd-4147-bebe-cb74e67ea3d3)

3. Paste the "Upload" folder into `C:\inetpub\wwwroot`.

![image](https://github.com/user-attachments/assets/8ecbca2c-ce0b-474f-b3ac-71efebff72d7)

4. Rename the "Upload" folder to "osTicket."

![image](https://github.com/user-attachments/assets/0911f001-1219-4faa-be34-900bc31a8429)

5. Open "IIS" and select "Stop/Start Server."

![image](https://github.com/user-attachments/assets/964768b8-b662-4127-8e10-30e6393906de)

6. In "IIS," select "Sites" > "Default Web Site" > "osTicket."

![image](https://github.com/user-attachments/assets/4086339b-22e2-442e-84cc-ec7f579e289b)

7. Open "PHP Manager."

![image](https://github.com/user-attachments/assets/016445d6-1fda-4688-8819-52e2253c0b74)

8. In "PHP Manager," select "Enable Extensions."

![image](https://github.com/user-attachments/assets/8dca965a-e8bd-42a4-a516-ebf0cd9a8327)

9. Enable the following extensions:
   - Enable: `php_imap.dll`
   - Enable: `php_intl.dll`
   - Enable: `php_opcache.dll`

![image](https://github.com/user-attachments/assets/0d3eba52-b1ef-4b72-a0d6-9d50527b5de3)


---

# Step 7 - Configure osTicket

1. Press "Windows Key + E" and go to `C:\inetpub\wwwroot\osTicket\include\ost-sampleconfig.php`.

![image](https://github.com/user-attachments/assets/20510de1-1f97-4db1-9fca-2e6c33f5cc8d)

2. Rename `ost-sampleconfig.php` to `ost-config.php`.

![image](https://github.com/user-attachments/assets/3fe6b144-bbdc-4b0a-bf5c-80d96777ddfa)

3. Right-click `ost-config.php` and select "Properties."

![image](https://github.com/user-attachments/assets/1bdd2000-5be1-4276-9d25-4ea52bdf5ce6)

4. Select "Security" and then "Advanced."

![image](https://github.com/user-attachments/assets/b5513153-666f-4a38-b37d-57456498c7cf)

5. Select "Add."

<img width="353" alt="image" src="https://github.com/user-attachments/assets/96cc8db2-611d-478b-bb22-f73100fc5788" />

6. Select "Principal," set it to "Everyone," and select "Full Control."

![image](https://github.com/user-attachments/assets/afa86136-8fc1-4738-971b-6c73d5b59dcf)

![image](https://github.com/user-attachments/assets/57dfcb1a-cb72-4256-bb4f-9188f48ae5f6)

7. Select "Apply."

![image](https://github.com/user-attachments/assets/5872babd-42bc-4f86-abae-6a1ae0026fc6)

8. Open a Web Browser, go to "[osTicket Installer](http://localhost/osTicket/setup/)," and select "Continue."

![image](https://github.com/user-attachments/assets/e5974610-578a-46d4-ac08-7d961fa7df41)

9. Name your "Helpdesk" and add an "Email."

![image](https://github.com/user-attachments/assets/f244632f-11cd-4dbf-be91-0b3b31066b4c)

10. Create an Admin with the following credentials:
    - Username: `Adminuser`
    - Password: `Password1`

![image](https://github.com/user-attachments/assets/cdf9ce82-7400-4549-b822-6edec5dd094a)


---

# Step 8 - Install HeidiSQL

1. Open the "osTicket-Installation-Files" folder and install "HeidiSQL."

![image](https://github.com/user-attachments/assets/db6496c8-c2d4-4ab1-9e63-56aefa284da1)

2. In "HeidiSQL," add a "New Session."

![image](https://github.com/user-attachments/assets/a9268f18-78a8-444a-9de3-17eeebee0cb1)

3. Use the following credentials and press "Open":
   - Username: `root`
   - Password: `root`

![image](https://github.com/user-attachments/assets/cf09b5bc-e54b-4bf5-8e4f-2633d280a653)

4. Right-click "Unnamed" and select "Create New" > "Database."

![image](https://github.com/user-attachments/assets/000105e9-8d51-42ce-84c9-12e11424ebde)

5. Name the database `osTicket`.

![image](https://github.com/user-attachments/assets/1c3f6415-cc4d-4d4c-90df-c2c5b7a3ac50)

6. Go back to the "Browser," use the following credentials to set up the database, and click "Install":
   - MySQL Database: `osTicket`
   - MySQL Username: `root`
   - MySQL Password: `root`
   
![image](https://github.com/user-attachments/assets/fcf0f0b3-af70-4dc4-88f2-b6256f34edbc)


---

# osTicket - Installation Complete

Use the following links to access the Helpdesk:

- **Admin**: [osTicket :: Admin Login](http://localhost/osTicket/scp/login.php)
  
- **Helpdesk**: [Helpdesk](http://localhost/osTicket/)

