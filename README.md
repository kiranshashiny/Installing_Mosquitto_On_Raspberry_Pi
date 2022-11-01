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


## To subscribe 

mosquitto_sub -d -t testTopic


## To publish

mosquitto_pub -d -t testTopic -m "Hello world!"

## To check if Mosquitto is actually running, you can run the following command:

sudo systemctl status mosquitto


