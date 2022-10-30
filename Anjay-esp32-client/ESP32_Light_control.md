## Light Control Setup :

1. First we need to complete the process from !(https://github.com/pschragger/IOT_Tutorials_for_VU/tree/main/RPI_BUILD_LWM2M_DEVICE)
2. To make sure the ESP32 can be found at the server. 
3. From the Freenova ultimate starter kit i have found how to setup an LED diagram in to the breadboard and connect it to the ESP32


## Light Control Setup Using Anjay ESP-32 LwM2M Client :
Following the ESP32 circuit connecion would be 

1. Inset the LED light in to the breadboard. 
2. Connect the long pin to LED(+) with a register (220 ohm)
3. Connect the Negative pin of the LED light with ground 
4. Connect the positive side of this LED light to  GPIO pin 2

After successfully connection it should look like this


After Sucessfull connection. 
1. Connect to your dietpi using ssh.
2. Go to projects and access the pre-installed anjay-esp32-client 
      $cd ~/projects/Anjay-esp32-client
3. Start another shell script and start the leshan server using the following command 
     
      cd ~/projects/leshan
      java -jar leshan-server-demo/target/leshan-server-demo-*-SNAPSHOT-jar-with-dependencies.jar &

You can also follow this URL if you did not install Leshan server with your diet pi 
  https://github.com/tanjina907/VU_FALL22_IOT_CLASS/tree/IoT_main/LWM2M%20installation%20and%20Experiements
  
5. Setup the local enironment for using the esp tools
      cd ~/projects/Anjay-esp32-client
      . $HOME/esp/esp-idf/export.sh
      idf.py set-target esp32 
6. Setup the device requirements 

    cd ~/projects/Anjay-esp32-client
    idf.py menuconfig
 
7. Go to Components > config/anjay-esp32-client
8. Setup your config to be: (anjay-esp32-client) Endpoint name (coap://{LESHAN_SERVER_IP}:5683) mine was coap://192.168.8.122:5683
9. 
