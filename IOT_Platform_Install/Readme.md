# Setup RPI software to run IoT platform #

 ## Procedures ## 
 
 After successfully seting up RPI software on using wifi. I can use Dietpi to install further software. 
 Do the followings to install the software:
 1. From your terminal window type ssh dietpi@RPI_address
 2. Your login shoul result in showing a command line like: dietpi@DietPiPAS:~$
 ## Installing the required software ##
 4. install software on the PI using dietpi-software command
  ![image1](/IOT_Platform_Install/Image/image07.png)
 4. Search for mqtt and select 123 MQTT message broker install by hitting the spacebar and selecting ok
    ![image1](/IOT_Platform_Install/Image/image08.png)
 5. Search for node-red and select "122 Node-RED: tool for wiring devices, APIs and online services" install by hitting the spacebar and selecting ok
  6. Search for postgress and select "194 PostgreSQL: Persistent advanced object-relational database server" install by hitting the spacebar and selecting   ok
    Move curser to Install and tab to ok
    Once you hit enter it should indicate:
     ![image1](/IOT_Platform_Install/Image/image11.png)
Click on Ok.
It should shows on the following tab 
![image1](/IOT_Platform_Install/Image/image12.png)

After sucessfull installation following screen should show 
![image1](/IOT_Platform_Install/Image/image14.png)
Please reboot the pi on the command line using reboot command and ssh. 
Make sure to use Sudo if you are using mac.


## Postgres ##
1.  Using sudo su postgres
2.  Create a user with :sudo createuser pi -P --interactive
3.  When prompted, enter a password (and remember what it is), select n for superuser, and y for the next two questions.
![image1](/IOT_Platform_Install/Image/image15.png)
4.  Now connect to Postgres using the shell and create a test database:
  psql
 sudo create database test;
 It should do the following 
 ![image1](/IOT_Platform_Install/Image/image16.png)
 
 5. Exit from the psql shell and again from the Postgres user
 Type : exit
 6. Now create a test database by doing the following command 
    sudo su postgres

    psql test

    create table people (name text, company text);
 7.Now add data by inserting the following command 

    insert into people values ('Ben Nuttall', 'Raspberry Pi Foundation');

    insert into people values ('Rikki Endsley', 'Red Hat');

  8. You can test that the data by the following command on your terminal

    select * from people;
It should shows the following 
![image1](/IOT_Platform_Install/Image/image17.png)
9.  Now restart the service by exiting back to the root console line by tyring exit 
    and type the following 
    dietpi-services restart postgresql
  
10.Check the log to see that the service started up tcp services we have  used:
sudo cat /var/log/postgresql/postgresql-13-main.log
This should show the following log file 
  ![image1](/IOT_Platform_Install/Image/image18.png)

## NODE-RED ##

1. Connect to node-red to see that it is running using it RPI Static IPaddr

   http://{YOUR_RPI_IPADDRESS}:1880
2. Install node-red-contrib-re-postgres in your ssh command line using:

  sudo npm install node-red-contrib-re-postgres

3.Restart node-red with the command

    sudo dietpi-services restart node-red
    
 This should show the following   
    ![image1](/IOT_Platform_Install/Image/image19.png)
    
  4. Go to Manage Pallet and install node-red-contrib-postgresql
    [image1](/IOT_Platform_Install/Image/image20.png)
   5.After installing it should shows the following 
    [image1](/IOT_Platform_Install/Image/image21.png)
   6. pull a postgres node into a flow
   7. Pull in a trigger and template node and debug node and wire
    trigger->template->Postgres->debug
It should show like this  
    ![image1](/IOT_Platform_Install/Image/image22.png)
    

Courtesy : This tutorial is made followed by (https://github.com/pschragger/IOT_Tutorials_for_VU/tree/main/RPI_IOT_PLATFORM_INSTALL_tutorial)
  
