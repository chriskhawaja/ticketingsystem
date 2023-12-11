

![image](https://github.com/chriskhawaja/ticketingsystem/assets/153021794/a4262750-495a-4fcd-81b0-7387b8fbca1e)





<h1>Creating and Managing a Help Desk Ticketing System</h1>

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

   




![image](https://github.com/chriskhawaja/ticketingsystem/assets/153021794/5bd9dc8e-c57d-4609-a931-a15accd266b9)
  - 
- Step 5
  - Once you are booted into the Virtual Machine, proceed to download Wireshark
  - Type in "Download Wireshark" on a Google Search
    ![image](https://github.com/chriskhawaja/azure-network-protocols/assets/153021794/0fb98c1c-7feb-4465-8ba6-9e4914726d40)

- Step 6
  - Once you are finished downloading Wireshark, boot up Wireshark by searching for the program towards the bottom left corner of the screen
  
   ![image](https://github.com/chriskhawaja/azure-network-protocols/assets/153021794/4929ebc0-2736-48f7-bec3-81b7cb40ae7a)

- Step 7
  - Once you are in Wireshark, be sure to select Ethernet
  ![image](https://github.com/chriskhawaja/azure-network-protocols/assets/153021794/f4463c38-3339-439e-9e2c-1ce43ee360a5)

- Step 8
  - You will begin to see multiple streams of network traffic be displayed
  - Above the network traffic, where it says "Apply a Display Filter" in the white box, type in whatever traffic you would like to be displayed
  - Have fun analyzing network traffic!
  - ![image](https://github.com/chriskhawaja/azure-network-protocols/assets/153021794/bd4a5ea6-9da4-4706-8a86-364312b0e281)

<h2>Project Demonstration</h2>

<p>

![image](https://github.com/chriskhawaja/azure-network-protocols/assets/153021794/0671b969-85bd-41ab-bcf3-0f04519b67ac)
  - We can see there is a connection established between VM1 and VM2 via the non-stop ping command
    - ping 10.0.0.5 -t
      - This command can be entered into command prompt by typing "cmd" in the start menu below
        - Make sure that before clicking cmd, right-click and select "run as administrator"
- 10.0.0.5 is the private IP Address of our Linux Virtual Machine

![image](https://github.com/chriskhawaja/azure-network-protocols/assets/153021794/aecc41e7-943b-488c-91b5-9365e1bfb142)
- We will now block this connection by going back to Microsoft Azure, and typing in "Network Security Groups" into the search bar
- On the left, we can click the "Inbound Security Rules" tab, and click the add button - this tab is selected because we want to block any ICMP traffic coming into VM2, hence the word "inbound"
- Be sure to select ICMP as the protocol and the deny option
  - ICMP stands for Internet Control Message Protocol, and is the protocol that is used when using the ping command
- Lastly, select the add button, and the security rule will be created

![image](https://github.com/chriskhawaja/azure-network-protocols/assets/153021794/ca61784b-48d5-4c3d-86fc-db57538c90a9)
- Now, we can observe that any traffic being sent to VM2 is being blocked

  ![image](https://github.com/chriskhawaja/azure-network-protocols/assets/153021794/25ae8002-6238-4782-bf84-f59863d0d4a3)
- We can reverse this process by going back to our NSG for VM2, selecting the rule we created, and clicking the allow button under ICMP
- Be sure to press "save" and the rule will be created

  ![image](https://github.com/chriskhawaja/azure-network-protocols/assets/153021794/7d98f982-45f0-4928-8eb8-1af9450b4d3b)
- We can see the replies from VM2 coming back after we changed the inbound rule 

![image](https://github.com/chriskhawaja/azure-network-protocols/assets/153021794/dcaf8831-58c9-4eee-8774-a0f187424535)
- Utilizing SSH, we can also acces the Linux terminal of VM2 from VM1
  - To access VM2 using VM1, be sure to input SSH Username@IP Address
    - The username and IP address of the VM that you are trying to access
   
![image](https://github.com/chriskhawaja/azure-network-protocols/assets/153021794/dcec2035-05ec-472a-8a8f-12645b2a06fc)
- Once we filter for Remote Desktop Protocol traffic, we can see the inundation of traffic
  - This is because we are literally using RDP to access our VM
 
  ![image](https://github.com/chriskhawaja/azure-network-protocols/assets/153021794/20ff0139-ebf7-4af2-b4e8-7e5ab8ac5f94)
- After visiting different websites on our VM, we can see all the DNS information on Wireshark
- Additionally after utilizing the command "ipconfig /displaydns", we can see that our cache is full of information

  ![image](https://github.com/chriskhawaja/azure-network-protocols/assets/153021794/4f6a5650-6f0a-46c3-ba8b-602a661b59c9)
- To flush our DNS cache, we can use the "ipconfig /flushdns" command
  - This command is really important when users are experiencing a multitude of DNS issues
 
![image](https://github.com/chriskhawaja/azure-network-protocols/assets/153021794/67e1cf2c-17f3-4859-8201-12f1d177169b)
- To view our DHCP and DNS servers, we can type the command "ipconfig /all" into command prompt

  ![image](https://github.com/chriskhawaja/azure-network-protocols/assets/153021794/e20a6d00-e5f7-4516-9a66-daf11afcfbaf)
- DHCP traffic can be analyzed by using the "ipconfig /release" and "ipconfig /renew" commands
  - The release command will tell our DHCP server to get rid of our current IP address, which was given to us via DHCP
  - The renew command will give us a new allocated IP address that is dynamically given via DHCP
  - Note that when you use these commands, your connection may be lost since we have "released" the VM's current IP address
 
  ![image](https://github.com/chriskhawaja/azure-network-protocols/assets/153021794/cad81990-28a6-4ddd-aea6-5eee091ed677)
  - You can now see in Wireshark, the steps of DHCP release and renewal
    - The DORA process highlights how a Client and DHCP Server communicate
      - Discovery, Offer, Request, and Acknowledge 
      
