# Installing_Mosquitto_On_Raspberry_Pi


## This link was used to install Mosquitto Broker on Raspberry Pi.

https://randomnerdtutorials.com/how-to-install-mosquitto-broker-on-raspberry-pi/

## Link to test the installation

https://randomnerdtutorials.com/testing-mosquitto-broker-and-client-on-raspbbery-pi/

To enable the username and password to authentication, use this command

![image](https://user-images.githubusercontent.com/14288989/199001486-c4c1ccb1-90e9-42dd-9472-507da3a623db.png)


sudo nano /etc/mosquitto/mosquitto.conf


## To start as a daemon

mosquitto -d

## To restart
sudo systemctl restart mosquitto


## To subscribe 
mosquitto_sub -d -t testTopic


## To publish
mosquitto_pub -d -t testTopic -m "Hello world!"

## To check if Mosquitto is actually running, you can run the following command:

sudo systemctl status mosquitto

Note : This will give old information also ! So check the current date on the Rpi and also the last date of the message in the above to know if it's really a problem.


## The location of the mosquitto installation is /etc/mosquitto

pi@raspberrypi:/etc/mosquitto $ ls
ca_certificates  certs  conf.d  mosquitto.conf  passwd


## To publish from command line on the Mac OS to the cloudmqtt.com platform
This will publish to the cloud mqtt broker.

mosquitto_pub -d -t testTopic -m "Hello world from Mosquitto Pub!" -h m12.cloudmqtt.com -p 19757 -u <User> -P <Password>


![image](https://user-images.githubusercontent.com/14288989/199173466-c2ad7e0e-d640-48ee-8b05-68587df053b3.png)


