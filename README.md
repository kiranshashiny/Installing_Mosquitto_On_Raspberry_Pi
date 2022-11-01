# Installing_Mosquitto_On_Raspberry_Pi


## This link was used to install Mosquitto Broker on Raspberry Pi.

https://randomnerdtutorials.com/how-to-install-mosquitto-broker-on-raspberry-pi/

## Link to test the installation

https://randomnerdtutorials.com/testing-mosquitto-broker-and-client-on-raspbbery-pi/

To enable the username and password to authentication, use this command

![image](https://user-images.githubusercontent.com/14288989/199001486-c4c1ccb1-90e9-42dd-9472-507da3a623db.png)


sudo nano /etc/mosquitto/mosquitto.conf


## To start as a daemon
```
mosquitto -d
```

## To restart
```
sudo systemctl restart mosquitto
```

## To subscribe 
```
mosquitto_sub -d -t testTopic
```

## To publish
```
mosquitto_pub -d -t testTopic -m "Hello world!"
```

## To check if Mosquitto is actually running, you can run the following command:
```
sudo systemctl status mosquitto
```
Note : This will give old information also ! So check the current date on the Rpi and also the last date of the message in the above to know if it's really a problem.


## The location of the mosquitto installation is /etc/mosquitto
```
pi@raspberrypi:/etc/mosquitto $ ls

ca_certificates  
certs  
conf.d  
mosquitto.conf  
passwd

```
## To publish from Raspberry Pi (where the Mosquitto client is installed) command line to the cloudmqtt.com platform

This will publish to the cloud mqtt broker.

```
mosquitto_pub -d -t testTopic -m "Hello world from Mosquitto Pub!" -h m12.cloudmqtt.com -p 19757 -u <User> -P <Password>
```

![image](https://user-images.githubusercontent.com/14288989/199173466-c2ad7e0e-d640-48ee-8b05-68587df053b3.png)


## Mosquitto Broker Enable Remote Access (Authentication: user and password)
```
sudo mosquitto_passwd -c /etc/mosquitto/passwd YOUR_USERNAME

e.g:

sudo mosquitto_passwd -c /etc/mosquitto/passwd sara
```


## To allow authentication with the username and password we’ve defined.
Add the following line at the top of the file (make sure it is at the top of the file, otherwise it won’t work):

```
sudo nano /etc/mosquitto/mosquitto.conf


per_listener_settings true
```

Add the following three lines to allow connection for authenticated users and tell Mosquitto where the username/password file is located.
```
allow_anonymous false
listener 1883
password_file /etc/mosquitto/passwd
```

## The default port that is used by mosquitto on Rpi.
```
1883
```

