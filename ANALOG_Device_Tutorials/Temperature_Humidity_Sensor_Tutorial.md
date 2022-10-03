# Temperature and Humidity sensor Using DHT11 and Raspberry pi 

## Hardware Requirements 

1. Raspberry pi 
2. DHT11 sensor 
3. Breadboard 
4. Jumber cables 
5. One 10 kiloOhm resistor 

The DHT11 has a surface mounted NTC thermistor and a resistive humidity sensor. An IC on the back of the module converts the resistance measurements from the thermistor and humidity sensor into digital temperature (in °C) and relative humidity measurements.

We have used the DHT11 sensor. Which have 4 pins. 

The follwoing is the pin details . 

The following are the pin details.
 1. VCC pin will connect  with pin no 2 on Raspberry pi for 5v Power
 2. Pin 2/ signal pin from the sensor will connect with pin no 7 on the Raspberry pi GPIO 4
 3. We would not connect anything with the Pin 3 of the sensor
 4. We will connect in 4 which is ground to pin 6 of RAspberry pi.





![image](https://github.com/tanjina907/VU_FALL22_IOT_CLASS/blob/0898d92619324389ab60d4f168804f7992567088/ANALOG_Device_Tutorials/Image/image5.png)

Using the following video i have connected my sensor with the pi and bread board.

https://www.youtube.com/watch?v=DPvxsHoD7kc
    
Below is my Breadboard sensor and Raspberry pi conenction :

![image](https://github.com/tanjina907/VU_FALL22_IOT_CLASS/blob/0898d92619324389ab60d4f168804f7992567088/ANALOG_Device_Tutorials/Image/image4.png)
Here is my Referal picture for the connection 

![image](https://github.com/tanjina907/VU_FALL22_IOT_CLASS/blob/0898d92619324389ab60d4f168804f7992567088/ANALOG_Device_Tutorials/Image/image6.png)


## Software Setup 
After connecting the Raspberry pi and sensor now we will program the DHT11.

## Programming the DHT11 With C
We’ll be using WiringPi to program the DHT11 in C. To run the C program we need to install wiringpi, on our Raspberry pi.

## Download and install wiringpi

To obtain WiringPi using GIT:
1. From terminal clone the addess using this command

        git clone git://git.drogon.net/wiringPi  
  
        cd wiringPi
  
        git pull origin
    
2.To build/install there is a new simplified script:

        cd wiringPi
      
        ./build
       
After sucessfull installation it will show the below message  :

![image](https://github.com/tanjina907/VU_FALL22_IOT_CLASS/blob/0898d92619324389ab60d4f168804f7992567088/ANALOG_Device_Tutorials/Image/image1.png)

3. Create a new file in Pi using the below command and paste the following  C program  and save and exit:

         $nano humidity.temp.c
  
4. The following image showing Software snippet showing GPIO setup and runtime looping and temperature reading and writing results to output:
![image](https://github.com/tanjina907/VU_FALL22_IOT_CLASS/blob/0898d92619324389ab60d4f168804f7992567088/ANALOG_Device_Tutorials/Image/image7.png)

5. Code showing an infinite loop to read the sensor data
![image](https://github.com/tanjina907/VU_FALL22_IOT_CLASS/blob/0898d92619324389ab60d4f168804f7992567088/ANALOG_Device_Tutorials/Image/image8.png)


6.Compile and execute the program using the following command

        $ gcc -o thumidity.temp humidity.temp.c -lwiringPi -lwiringPiDev
        
        $ sudo ./humidity.temp
        
Below is my temparature output :

![image](https://github.com/tanjina907/VU_FALL22_IOT_CLASS/blob/0898d92619324389ab60d4f168804f7992567088/ANALOG_Device_Tutorials/Image/image3.png)

### Funny Experiment :
To test the sensor is working fine, i blow near the sensor and as you can see the last couple outputs for Humidity and Temparature has been changed surprisingly. 

## Blog 
https://computing-sciences.yellowdig.app/community/62e2eacc-366d-319c-a96d-cf1e0b1d27ef?postId=47424135935176784
## Alternate tutorial 

## Reference 
Freenove C tutorial downloaded from: https://freenove.com/fnk0047/
https://www.circuitbasics.com/how-to-set-up-the-dht11-humidity-sensor-on-the-raspberry-pi/

  
