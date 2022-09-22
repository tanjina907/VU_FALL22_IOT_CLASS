
# LWM2M Installation #

## Steps to follow :

1. First connect your Raspberry pi with your wifi network and log in to your Rasberry pi using Diet pi.

To install development environment on RPI 

## Install git :
1. From your terminal login to diet pi 
2. To search software type  sudo dietpi-software
3. Type git 
4. tab to ok and press enter

![image](https://github.com/tanjina907/VU_FALL22_IOT_CLASS/blob/364858deabc08ca2c53f3a801cadd14655f4fbbd/LWM2M%20installation%20and%20Experiements/Image/image1.png)
 
 5. Navigate to install on dietpi-software menu page
 6. Press enter and it should show that the software
 ![image](https://github.com/tanjina907/VU_FALL22_IOT_CLASS/blob/364858deabc08ca2c53f3a801cadd14655f4fbbd/LWM2M%20installation%20and%20Experiements/Image/image2.png)
 
 7. click on Ok.
 ![image](https://github.com/tanjina907/VU_FALL22_IOT_CLASS/blob/364858deabc08ca2c53f3a801cadd14655f4fbbd/LWM2M%20installation%20and%20Experiements/Image/image4.png)
 8. After some minitues it will install successfully. 
 9. Check that is installed by using the command on the pi

        git --version
        
        
       ![image](https://github.com/tanjina907/VU_FALL22_IOT_CLASS/blob/364858deabc08ca2c53f3a801cadd14655f4fbbd/LWM2M%20installation%20and%20Experiements/Image/image5.png)
  
  
  ## Install JAVA
  
  1.On command line in dietpi start dietpi-software

          sudo dietpi-software

   2. Search for Java JDK 
    Use spacebar to select ( asterick [*] should show
![image](https://github.com/tanjina907/VU_FALL22_IOT_CLASS/blob/IoT_main/LWM2M%20installation%20and%20Experiements/Image/image6.png)

3.click on Ok to install this software. 
![image](https://github.com/tanjina907/VU_FALL22_IOT_CLASS/blob/364858deabc08ca2c53f3a801cadd14655f4fbbd/LWM2M%20installation%20and%20Experiements/Image/image8.png)
After Successfull installation, check that is installed by using the command on the pi
    java --version

 ![image](https://github.com/tanjina907/VU_FALL22_IOT_CLASS/blob/364858deabc08ca2c53f3a801cadd14655f4fbbd/LWM2M%20installation%20and%20Experiements/Image/image9.png)
 
 
 ## Install maven 
 
1.In the dietpi directory create a download directory

  mkdir download

2. Change directory into the download directory

  cd download
  ![image](https://github.com/tanjina907/VU_FALL22_IOT_CLASS/blob/364858deabc08ca2c53f3a801cadd14655f4fbbd/LWM2M%20installation%20and%20Experiements/Image/image10.png)

3. Download the latest maven tarball using wget.
4. Unpack the tarball
   tar xzvf apache-maven-3.8.6-bin.tar.gz
5. Add the bin directory to the path
    echo 'PATH="${PATH}:~/download/apache-maven-3.8.6/bin"' >>  ~/.bashrc
6. Test maven installation using 
      bash
      mvn -v
  Also java home 
      echo $JAVA_HOME , 
      the follwoing result should show
     ![image](https://github.com/tanjina907/VU_FALL22_IOT_CLASS/blob/364858deabc08ca2c53f3a801cadd14655f4fbbd/LWM2M%20installation%20and%20Experiements/Image/image12.png)
   
   
   ## install leshan git and build
   
   1.Clone the leshan repo using

          cd
          mkdir projects
          cd projects
          git clone https://github.com/eclipse/leshan.git
       
![image](https://github.com/tanjina907/VU_FALL22_IOT_CLASS/blob/IoT_main/LWM2M%20installation%20and%20Experiements/Image/image11.png)

2. After cloning successfully build the leshan using the follwoing command 
      build leshan

      cd ~/projects/leshan
      mvn clean install
      
   It will take 15 to 20 minutes for the build.
   
   ![image](https://github.com/tanjina907/VU_FALL22_IOT_CLASS/blob/364858deabc08ca2c53f3a801cadd14655f4fbbd/LWM2M%20installation%20and%20Experiements/Image/image13.png)
   
   3.Start the server using

        cd ~/projects/leshan
        java -jar leshan-server-demo/target/leshan-server-demo-*-SNAPSHOT-jar-with-dependencies.jar &

   Connect on Leshan demo UI: http://RPI_IPADDR:8080

My RPI address was 192.168.8.122 so i use 192.168.8.122:8080

this will bring up te leshan register client page
![image](https://github.com/tanjina907/VU_FALL22_IOT_CLASS/blob/364858deabc08ca2c53f3a801cadd14655f4fbbd/LWM2M%20installation%20and%20Experiements/Image/image14.png)
 4.Run the leshan client to add it to the page

java -jar leshan-client-demo/target/leshan-client-demo-*-SNAPSHOT-jar-with-dependencies.jar
 Go to the page again 
 192.168.8.122:8080
 Now the dietpi will show as a client end point 
![image](https://github.com/tanjina907/VU_FALL22_IOT_CLASS/blob/364858deabc08ca2c53f3a801cadd14655f4fbbd/LWM2M%20installation%20and%20Experiements/Image/image15.png)

The following tutorial is made with the help of !(https://github.com/pschragger/IOT_Tutorials_for_VU/tree/main/RPI_DEVICE_MANAGEMENT_INSTALL_tutorial).

Thank you!
