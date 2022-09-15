# Setting up Raspberry PI  using dietpi via wifi #

In this tutorial we will perform an initial install of DIET_PI on a Raspberry PI 4 model u uinsting your WIFI setup router.

## Process 
1. Flash diet-pi image on our SD card.
2. Install SD card on our Raspberry pi -4 model b. 
3. Setup Raspberrypi using the wifi router.


## Prerequisites  ##

 1. A laptop or desktop 
 2. A Raspberry PI  4 
 3. A microSD card at least 8 GB
 4. WIFI ROUTER Which we have been setup befor(In this case i am using Travel Mango router)

## Performed  Steps ##
1. First downloaded dietpi image based on your pi. I have downloade Amiberry ARMv7  as it was supported via my Raspberry pi 4 model B.
2. Download Balena Etcher to Flash SD Card 
3. Open balena etcher and select the download dietpi image and target SD card. click on Flash. It will take some minitues to flash the SD card. 
4. After flashing the SD card 
Edit your Diet-wifi.txt file and Diet.txt fil. Configure the boot image on the microSD card of dietpi.
   - copy dietpi.txt and dietpi-wifi.txt to a temporary directory
   - edit dietpi-wifi.txt with your router ssid and creadentials
      Change the lines:
      ```
      aWIFI_SSID[0]=''
      aWIFI_KEY[0]=''
      ```
      adding your SSID and ssid_password for example SSID=IOT-PAS and password=iotlogin would result in the lines:
      ```
      aWIFI_SSID[0]='IOT-PAS'
      aWIFI_KEY[0]='iotlogin'
      ```
   - edit dietpi.txt with your location and wifi network default settings
     For the East Coast US settings change the values of the variables listed below
      ```
      AUTO_SETUP_LOCALE=en_US.UTF-8
      AUTO_SETUP_KEYBOARD_LAYOUT=us
      AUTO_SETUP_TIMEZONE=America/New_York
      AUTO_SETUP_NET_ETHERNET_ENABLED=0
      AUTO_SETUP_NET_WIFI_ENABLED=1
      AUTO_SETUP_NET_WIFI_COUNTRY_CODE=US
      AUTO_SETUP_DHCP_TO_STATIC=1
      AUTO_SETUP_NET_HOSTNAME=DietPi_{YOUR_INITIALS}
      AUTO_SETUP_HEADLESS=1
      AUTO_SETUP_AUTOSTART_TARGET_INDEX=1
      SURVEY_OPTED_IN=0
      CONFIG_SERIAL_CONSOLE_ENABLE=1
      ```
      - be sure to replace {YOUR_INITIALS} with a locally unique string for me I used PAS so my pit is names DietPi_PAS.
      - search for each variable before the = and put in the new value in the file.
      - be sure to save the changes
5. Copy the dietpi.txt and dietpi-wifi.txt you edited to the top level directory of your sd card.es. This process has been followed by this tutorial 
(https://github.com/tanjina907/IOT_Tutorials_for_VU/blob/f3c5c4314b8bbf52c5d0a3f4e950ec187f21d125/RPI_BOOT_WIFI_tutorial/README.md)

6. Eject the SD card from your computer. 
7. Insert SD card in to Raspberry pi. After given power to the Raspberry pi, it will start to flashing a yelllow light beside the red light. 
8. It will take 5 to 10 minitues to install the SD card. And the yellow light will finish flashing.
9. Go to your Wifi router admin pannel. 
10. You will find Dietpi into the client tab.

![image1](/RPI_tutorial/Image/image01.png)

## Setup RPI from Laptop ##
1. Use SSH login to login in to RPI network 
2.Use the below Username =SSH@root(RPI address)
4. Password = dietpi
   
   Make sure to change your root login user name and password during setup
![image1](/RPI_tutorial/Image/image04.png)

After sucessfully changing the password, you can see your full RPI installed.

![image1](/RPI_tutorial/Image/image05.png).

Enjoy!
The next step is to Install the IoT setup.
