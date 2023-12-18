

![image](https://github.com/chriskhawaja/ticketingsystem/assets/153021794/a4262750-495a-4fcd-81b0-7387b8fbca1e)





<h1>Creating and Administering a Help Desk Ticketing System</h1>

<h2>Project Summary</h2>
This project involves the creation of a Help Desk ticketing system with the use of an Azure virtual machine. Additionally, there will be a significant amount of programs that will need to be downloaded. Specifically, we will need to enable Internet Information Services (IIS), and dowload programs such as PHP manager for IIS, MySQL, HeidiSQL, osTicket software, visual C++ distributable, and URL rewrite. Once the ticketing system is created, we can create different departments, roles, teams, agents, and users. Additionally, we can create help topics when users submit tickets, and create Service Level Agreements (SLA's) based on the severity of different tickets. Furthermore, we can act as users by submitting tickets, and then respond to those tickets by using administrator accounts. The goal of this project is to educate individuals on the administration of ticketing systems, and provide experience in the creation and response of ticket requests. 
<h2>Platforms and Technologies Used</h2>

- Microsoft Azure (Virtual Machine Deployment)
- Azure Resource Group (Contains VM)
- RDP (Remotely Accessing Virtual Machines)
  - TCP Port 3389
- Internet Information Services
- PHP Manager
- HeidiSQL
- MySQL
- Visual C++ Distributable
- URL Rewrite
<h2>Operating Systems Used </h2>

- Windows 10 Pro (2-4 vCPU's)

<h2>Project Installation Steps</h2>

- Step 1
  - Create a Resource Group within Microsoft Azure
![image](https://github.com/chriskhawaja/ticketingsystem/assets/153021794/88698d6a-43ad-430f-b331-c399cd577884)


- Step 2  - within the Resource Group that was created
  - Create an Azure Virtual Machine running a Windows 10 Pro Image
  - Make sure to place this Virtual Machine into the resource group that was created
![image](https://github.com/chriskhawaja/ticketingsystem/assets/153021794/0f60f238-cbfe-40fd-a5b3-4568c566de05)


- Step 3
 - Remote into the VM by using Remote Desktop Protocol 
  - If there is confusion on how to do this, please refer to the other labs for assistance
![image](https://github.com/chriskhawaja/ticketingsystem/assets/153021794/7dafb199-6ac0-455a-aa33-d32b74ca1faa)



- Step 4
   - Type in "run" at the start menu on the bottom left corner
   - Once the run box comes up, type "control panel" and press enter

    ![image](https://github.com/chriskhawaja/ticketingsystem/assets/153021794/c6aa20ed-95ce-4084-b6cb-0ba6c3ddc0d4)
  - When control panel loads up, clikc "Programs"
  - Then select "Turn Windows features on or off"
![image](https://github.com/chriskhawaja/ticketingsystem/assets/153021794/ebb6436d-e9f5-4b64-afb6-fe90e1d71a1b)
  - Make sure that Internet Information Services is selected
  - Expand World Wide Web Services, click Application Development Features, and make sure that CGI and Common HTTP Features are selected
![image](https://github.com/chriskhawaja/ticketingsystem/assets/153021794/524a3f4f-fd28-4833-85f7-4f47cb292ea1)
  - Additionally, make sure that IIS Management Console is selected under Web Management Tools
  - When finished, press "ok" and changes will be made
  - We will now begin by downloading PHP 7.38
![image](https://github.com/chriskhawaja/ticketingsystem/assets/153021794/b3021099-62bc-4982-bb43-6398b1f5f8b0)
  - After downloading PHP 7.38, we need to create a PHP folder in our C: Drive
![image](https://github.com/chriskhawaja/ticketingsystem/assets/153021794/b54bb74c-9fd3-4039-82f8-d0626365e6dc)
  - Next, we will download the Rewrite Module
  - Run the Rewrite Module Setup Wizard and finish the installation
![image](https://github.com/chriskhawaja/ticketingsystem/assets/153021794/c139c988-6dcf-46d7-a1d2-adeb45ba61d8)
  - We will now download PHP Manager for IIS
  - Run and complete the PHP Manager for IIS Installation Wizard
![image](https://github.com/chriskhawaja/ticketingsystem/assets/153021794/94569378-4585-4b0a-ac26-e473c0b065ee)
  - We will now extract the zipped PHP 7.38 folder into the empty PHP folder in our C: Drive
  ![image](https://github.com/chriskhawaja/ticketingsystem/assets/153021794/f7baf457-355c-43c5-b206-5913562f26ba)
  - Run the Visual C++ Setup Wizard and finish the installation
  - Next, download MySQL and proceed with the "Typical Setup" and install
    - Once the configuration wizard launches, select "Standard Configuration" and select a password
  ![image](https://github.com/chriskhawaja/ticketingsystem/assets/153021794/2fa48bd6-c515-4c4d-afc7-3fe99d51ec5e)
  - Select execute and finish the installation 
  - We will now type in IIS at the start menu and right-click over IIS (run as administrator)
![image](https://github.com/chriskhawaja/ticketingsystem/assets/153021794/09714785-5a2d-4bee-80df-12cc98bcee38)
  - Double-click PHP and select "Register new PHP version"
  - Select the cgi file from the PHP folder that received the extracted files 
![image](https://github.com/chriskhawaja/ticketingsystem/assets/153021794/4f6d7a0b-0d44-4bc4-8e57-e1b6b90efa2f)
  - Stop and restart the PHP server (found towards the right side of IIS)
  - Next, install osTicket
  - Drag upload folder from osTicket zipped folder into "wwwroot"
    - This is found within the "inetpub" folder of the C: drive on the VM
![image](https://github.com/chriskhawaja/ticketingsystem/assets/153021794/108d481b-e402-463c-a95c-97c57d7e5689)
  - VERY IMPORTANT! - Rename upload folder in wwwroot to "osTicket"
    - If this is not done, the ticketing system will not work
  - Reload IIS as administrator
    - Select osTicket -> Sites -> Default Web Site -> osTicket folder -> Browse *:80(http)
    - osTicket installer should now load up (some extensions are not enabled)
![image](https://github.com/chriskhawaja/ticketingsystem/assets/153021794/62ce7539-d4fd-4f5d-9738-1f70afb8d354)
  - to enable these extensions, open IIS back up, and navigate to the osTicket folder
  - Open PHP Manager
  - Click "enable or disable an extension" at the bottom
  - Enable the "impap, intl, and opcache" extensions
![image](https://github.com/chriskhawaja/ticketingsystem/assets/153021794/79e7278f-92ac-4515-8888-853bcdf866c1)
  - Refreshing the osTicket installer on your web browser should show those extensions enabled
  - Next, rename ost-sampleconfig.php to ost-config.php (found within the "include" folder within osTicket folder of wwwroot)
  - Next, give everyone access to the ost-config.php file
 ![image](https://github.com/chriskhawaja/ticketingsystem/assets/153021794/f94b6206-1ec5-453c-af75-c6959f885e36)
  - Continue to fill out os Installer information, such as Help Desk name and Administrator account information
![image](https://github.com/chriskhawaja/ticketingsystem/assets/153021794/f329db4c-25ee-46c4-8661-1aed8ba7f2a2)
  - Run and install HeidiSQL
  - Create a new session for root and create a password
![image](https://github.com/chriskhawaja/ticketingsystem/assets/153021794/75987d66-57bd-4248-a610-ce1d750ef396)
  - Right-click on "Unnamed"
  - Select New -> Database
  - Name it osTicket
![image](https://github.com/chriskhawaja/ticketingsystem/assets/153021794/4ccb7533-b770-4973-9d40-d92b3e463d55)
  - Fill out the database settings on osInstaller and click "Install"
  - Login to your Help Desk system with the administrator account you created
    - http://localhost/osTicket/scp/login.php
  - The Help Desk system is now created
![image](https://github.com/chriskhawaja/ticketingsystem/assets/153021794/c2cf290f-f777-4562-90a6-c618ea48b8b6)


   <h2>Setting up the Ticketing System</h2>

- Configuring Roles
  - Switch to the Admin Panel -> Select Agents -> Select Roles
  - We will create a Super Administrator role that has all privileges
![image](https://github.com/chriskhawaja/ticketingsystem/assets/153021794/1bea6ba1-cc3f-4ff3-8e97-8e85776dd268)

- Configuring Departments
  - Admin Panel -> Agents -> Departments
  - We wil create two Departments (System Administrators and Network Administrators)
![image](https://github.com/chriskhawaja/ticketingsystem/assets/153021794/1e1ca7b1-8ccb-4bed-aa1d-f51fb5c8c8bf)
![image](https://github.com/chriskhawaja/ticketingsystem/assets/153021794/2178a038-7af7-4cfb-b48f-a51e2d1fc2f8)

- Configuring Teams
  - Admin Panel -> Agents -> Teams
  - We will create Level II and III Support
![image](https://github.com/chriskhawaja/ticketingsystem/assets/153021794/0d51bcb3-046d-4ea9-9889-26da6e19860d)
![image](https://github.com/chriskhawaja/ticketingsystem/assets/153021794/1eaf3c42-8a3c-49bb-bbce-621428764d81)

- Configuring Agents (Help Desk Workers)
  - Admin Panel -> Agents -> Add New
  - We will create accounts for Jane and John Doe
![image](https://github.com/chriskhawaja/ticketingsystem/assets/153021794/603fbcce-14c2-4c74-9941-5198aa1fea76)

- Configuring Users (Customers)
  - Admin Panel -> Users -> Add New
  - We will create user accounts for Karen Doe and Ken Doe
![image](https://github.com/chriskhawaja/ticketingsystem/assets/153021794/73df9f5a-0fb2-40ce-873c-070921bcfb92)
![image](https://github.com/chriskhawaja/ticketingsystem/assets/153021794/8c2cd9eb-85cb-4b4e-96cb-bfdb2499ea71)

- Configuring Service Level Agreements
  - Admin Panel -> Manage -> SLA
  - We will create Sev-A (1 hr, 24/7), Sev-B (4 hrs, 24/7), and Sev-C (8hrs, business schedule)
![image](https://github.com/chriskhawaja/ticketingsystem/assets/153021794/d3f9fa0e-738a-4431-99ba-bbdf70fc9243)
![image](https://github.com/chriskhawaja/ticketingsystem/assets/153021794/91c0c804-8e38-4530-aded-ea15a9bd5e0e)

- Configuring Help Topics
  - Admin Panel -> Manage -> Help Topics
  - We will create Help Topics for Business Critical Outages, Password Resets, Equipments Requests, and Personal Computer Issues
![image](https://github.com/chriskhawaja/ticketingsystem/assets/153021794/dc390088-6bd5-426d-a223-7d9260a42ee8)

- Practice Help Desk Ticket
  - We will create and respond to a ticket for a practice simulation
![image](https://github.com/chriskhawaja/ticketingsystem/assets/153021794/cd3807a3-d197-4db7-a443-f7235d51a503)
![image](https://github.com/chriskhawaja/ticketingsystem/assets/153021794/e12291f0-198f-4e70-b4bc-bed42da3fb8f)
![image](https://github.com/chriskhawaja/ticketingsystem/assets/153021794/1c0c7c3f-e123-405b-981b-0c3a9b351ec9)

 

