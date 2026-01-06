# linux_assignment_HeroVired
This is assignment repository on topic Linux and servers

Task 1: System Monitoring Setup
-----------------------------------------------------
Configure monitoring to ensure system health, performance tracking, and capacity planning.

  a.Install & configure htop or nmon to track CPU Usage,Memory Usage and process activity
  
  b.Monitor disk usage using df (filesystem usage) & du (directory usage)
      <img width="903" height="423" alt="Task1" src="https://github.com/user-attachments/assets/4701ae3a-aa51-4c50-81d7-e2c6a5b46514" />
      
  c.Save monitoring outputs to log files for reporting
    <img width="1317" height="567" alt="Task1 1" src="https://github.com/user-attachments/assets/84114f19-d714-4d46-84be-0015d9097a31" />

Task 2: User Management & Access Control
----------------------------------------------------
Create and secure user accounts and workspaces for Sarah and Mike.

  a.Create system users: Sarah & Mike
  
  b.Create Workspaces :Sarah → /home/Sarah/workspace ; Mike → /home/mike/workspace
  
  c.Only the respective user should access each directory
  <img width="652" height="182" alt="Task2 1" src="https://github.com/user-attachments/assets/41063b5d-5f1d-45a4-9c27-b7c9acfa467a" />

  d.Enforce password expiration every 30 days
    <img width="1297" height="815" alt="Task2" src="https://github.com/user-attachments/assets/ad262f57-e04d-4c91-9ce2-1be5044f0e53" />

Task 3: Backup Configuration for Web Servers
----------------------------------------------------
Configure automated backups for Sarah’s Apache server and Mike’s Nginx server.

 a.Sarah manages Apache server & backup path :/etc/httpd/ ; /var/www/html/ ;
 <img width="886" height="182" alt="Task 3_apache" src="https://github.com/user-attachments/assets/5ec69512-463d-4a79-b6e4-e1c9cf7db975" />

 b.Mike manages Nginx server & backup path :/etc/nginx/ ; /usr/share/nginx/html/ ;
 <img width="1128" height="247" alt="Task 3_nginx" src="https://github.com/user-attachments/assets/bbd67ebd-cfb3-41ff-b3fe-01f0af83c141" />

 c.Use cron jobs : Run backups every Tuesday at 12:00 AM
 <img width="738" height="111" alt="Task 3_crontab" src="https://github.com/user-attachments/assets/f687f2e0-a963-43ab-8b02-e6f2944c5f2e" />
 
 Running at now :
 <img width="1155" height="797" alt="Task 3 1" src="https://github.com/user-attachments/assets/772d3a14-5084-430f-acdf-ed751bae531c" />

 d.Save backups in /backups/ & After each backup , Validate archive contents using listing commands
 
  Apache Backup :
    <img width="1181" height="498" alt="Task 3 2" src="https://github.com/user-attachments/assets/27dc797b-e7f2-44cd-8354-68504b608c33" />

  Nginx Backup :
    <img width="1186" height="492" alt="Task 3 3" src="https://github.com/user-attachments/assets/2e1e203f-ff74-4c58-adbe-435554a2efae" />

Challenges Faced During Implementation:
-------------------------------------------
  1.Issue:While installing htop and nmon using the yum install command, the installation failed because the packages were not available or supported through yum.
    <img width="1327" height="836" alt="Task1 2" src="https://github.com/user-attachments/assets/073414e5-2547-4ae7-99a8-68cba09c87ac" />
    
    Resolution:Switched to the dnf package manager and successfully installed the tools using:dnf install htop

  2.Issue:While installing and configuring the Apache server, the Apache service failed to start. This occurred because both Apache and Nginx were trying to use Port 80, causing a port conflict.
  
    <img width="1372" height="550" alt="Task3" src="https://github.com/user-attachments/assets/7e5f4b00-64a5-48f9-8518-82fe48b02fb5" />
    
    Resolution:Apache listening port was changed from Port 80 to Port 8080 in the configuration file. After updating the port and restarting the service, Apache started successfully while Nginx continued running on Port 80.
   Apache Server:
    <img width="1298" height="372" alt="Task3 4ap" src="https://github.com/user-attachments/assets/1b627b44-517b-4843-a5d7-7599d864e25d" />

   Nginx Server :
    <img width="1132" height="373" alt="Task3 5ngin" src="https://github.com/user-attachments/assets/421ede83-8224-4fc7-b7e9-5027ca40153b" />

